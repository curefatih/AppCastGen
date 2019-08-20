# HLS - HTTP Live Streaming

HLS sends audi and video over HTTP from an ordinary web server. Implmented by Apple Inc. as part of its QuickTime, Safari, OS X and IOS software and now avaliable in Microsot Edge, Firefox and some versions of Google Chrome

## Arhitecture

HLS uses a conventional web server to distribute audiovisiual contetnt and requires spesific software to fit into proper format transmission in realtime.
The service arhitecture comprises:

- Server

  Codify and encapsualer the input video flow in a proper format for the delivery.

  - Encoder:

    Codify video files in H.264 format and audio in AAC, MP3, AC-3 or EC-3. This is encapsulated by __MPEG-2 TRANSPORT STREAM__

  - Segmenter:

    Divides the MPEG-2 TS file into fragments of equal length, kept as **`.ts`** files. **It also creates an index file that contains references of the fragmented filex, saved as `.m3u8`**

- Distributor

  Formend by a standard web server, accepts request from clients and delivers all the resources __(`.m3u8` playlist file and `.ts` segment files)__ needed for streaming

- Client

  Request and download all the files and resources, assembling them so that can be presented to the user as a continous flow video. The client software downloads first the index file through a URL and then the several media files available. The playback software assembes the sequence to allow continued display to user.

## See also:

  ### Low Latency HLS (LHLS)

  Low Latency HLS which reduces the glass-to-glass delay when streaming via HLS by reducing the time to start lic estream playbacks and main tain that time during a live streaming event. It works by adding partial midea segment files into the mix, ala CMAF fMP4 (fragmented MP4), but unlike CMAF also suppors partial MPEG2 TS transport files. HTTP/2 is required to push the segments alog with the playlist, reducing the overhead of establishing repeated HTTP/TCP connections.\
  Also other features:\
  - Playlist Delta Updates
  - Blocking of playlist reload
  - Rendition Reports  


> [reference: Apple](https://developer.apple.com/documentation/http_live_streaming)

> [refecence: Wikipedia](https://en.wikipedia.org/wiki/HTTP_Live_Streaming)
