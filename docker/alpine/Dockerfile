FROM alpine:3.20

WORKDIR /opt

RUN apk add --no-cache \
    curl unzip ffmpeg \
    openjdk21-jre-headless \
    libx11 glib libstdc++ \
    libgcc ttf-dejavu \
    ca-certificates gcompat bash && \
    update-ca-certificates

RUN bash -c 'for i in 1 2 3 4 5; do \
    curl -L --fail --show-error -o yawcam-ai.zip \
    https://github.com/yawcam/yawcam-ai/releases/latest/download/yawcam-ai-linux-x64.zip \
    && break || echo "Retry ($i)..." && sleep 3; done'

RUN unzip yawcam-ai.zip -d /opt/yawcam-ai && \
    rm yawcam-ai.zip

# ❗ remove bundled JRE because it's GLIBC only
RUN rm -rf /opt/yawcam-ai/yawcam-ai/jre

# ❗ patch script properly: force java path detection override
RUN sed -i '/JAVA=.*/d' /opt/yawcam-ai/yawcam-ai/YawcamAi-console.sh && \
    sed -i '1i JAVA="/usr/lib/jvm/java-21-openjdk/bin/java"' /opt/yawcam-ai/yawcam-ai/YawcamAi-console.sh

RUN chmod +x /opt/yawcam-ai/yawcam-ai/YawcamAi-console.sh

ENV PATH="/usr/lib/jvm/java-21-openjdk/bin:${PATH}"

WORKDIR /opt/yawcam-ai/yawcam-ai

EXPOSE 5995 9081 9082

ENTRYPOINT ["./YawcamAi-console.sh"]
