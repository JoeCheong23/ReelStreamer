FROM ubuntu:24.04

RUN apt update
RUN apt install -y ffmpeg

WORKDIR /media
COPY test.mp4 .

# ENTRYPOINT ffmpeg -re -stream_loop -1 -i test.mp4 -c:v libx264 -c:a aac -f flv rtmp://nginx-c/hls/my-video
# ENTRYPOINT ["ffmpeg", "-re", "-stream_loop", "-1", "-i", "test.mp4", "-c:v", "libx264", "-preset", "veryfast", "-tune", "zerolatency", "-c:a", "aac", "-f", "flv", "rtmp://nginx/hls/my-video"]
ENTRYPOINT ["ffmpeg", "-re", "-stream_loop", "-1", "-i", "test.mp4", \
    "-c:v", "libx264", "-preset", "ultrafast", \
    "-tune", "zerolatency", \
    "-g", "15", \
    "-sc_threshold", "0", \
    "-c:a", "aac", "-b:a", "128k", "-ac", "2", \
    "-f", "flv", "rtmp://nginx/hls/test"]