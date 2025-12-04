FROM ubuntu:22.04

ENV DEBIAN_FRONTEND=noninteractive
WORKDIR /opt

# install system dependencies
RUN apt-get update && \
    apt-get install -y \
    curl unzip libgtk2.0-0 libasound2 libxtst6 libx11-6 \
    ffmpeg v4l-utils libgl1 && \
    rm -rf /var/lib/apt/lists/*

# Download latest YawcamAI linux release
RUN curl -L -o yawcam-ai.zip \
    https://github.com/yawcam/yawcam-ai/releases/latest/download/yawcam-ai-linux-x64.zip && \
    unzip yawcam-ai.zip -d /opt/yawcam-ai && \
    rm yawcam-ai.zip && \
    chmod +x /opt/yawcam-ai/yawcam-ai/YawcamAi.sh && \
    chmod +x /opt/yawcam-ai/yawcam-ai/YawcamAi-console.sh

# working dir inside app folder
WORKDIR /opt/yawcam-ai/yawcam-ai

# expose web UI ports
EXPOSE 9000 9081 9082

# entrypoint for console mode
ENTRYPOINT ["./YawcamAi-console.sh"]
