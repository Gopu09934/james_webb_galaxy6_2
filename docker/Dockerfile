FROM ubuntu:24.04
ENV DEBIAN_FRONTEND=noninteractive
RUN apt-get update && \
    apt-get install -y \
        ffmpeg \
        curl \
        ca-certificates && \
    rm -rf /var/lib/apt/lists/*
WORKDIR /app

# Copy the entire build context instead of naming files one by one.
# This automatically picks up everything the script can use — start.sh,
# overlay.png, font.ttf, galaxy_info.txt, facts.txt, and any per-video
# *.labels.txt / *.headlines.txt / *.facts.txt files — without needing
# a Dockerfile edit every time you add a new one.
COPY . .

RUN chmod +x start.sh
CMD ["./start.sh"]
