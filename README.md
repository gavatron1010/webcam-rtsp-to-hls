# webcam-rtsp-to-hls

The Dockerfile is based upon a AWS Kinesis doc https://docs.aws.amazon.com/kinesisvideostreams/latest/dg/examples-rtsp.html

I was able to make it happen with the GStreamer command: gst-launch-1.0 -v -e rtspsrc protocols=tcp location=rtsp://184.72.239.149/vod/mp4:BigBuckBunny_115k.mov ! queue max-size-time=100000000 ! rtph264depay ! h264parse ! mpegtsmux ! hlssink location="/opt/vid/%06d.ts" playlist-location="/opt/vid/playlist.m3u8" target-duration=5

![alt text](https://raw.githubusercontent.com/gavatron1010/webcam-rtsp-to-hls/master/demo.gif)