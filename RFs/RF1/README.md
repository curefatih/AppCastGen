# RF1
reference folder for the HLS experiment

usage steps

  - need a stream. for this purpose we used ffmpeg streming via terminal command\
  `ffmpeg -i 50.50.2011.720p.BrRip.x264.YIFY.mp4 -v 0 -vcodec libx264 -f mpegts udp://127.0.0.1:23000`
  
  - and for the HLS need to run `stream.sh`. Before running check for the streaming address on `VIDSOURCE` variable.

  - run `hls.html` on a server for the CORS purpose.

  - enjoy with the stream