FROM ubuntu:16.04 

RUN apt-get update && \
    apt-get install -y wget python3 python3-pip ffmpeg && \
    pip3 install yle-dl && \
    rm -rf /var/lib/apt/lists/* 

WORKDIR /app

ENTRYPOINT ["yle-dl"]

