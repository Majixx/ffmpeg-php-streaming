# FFMpeg-PHP Real-Time Video Streaming Tool

This is a real-time decoding and streaming tool written in PHP based on FFMpeg. It uses HLS protocol to stream videos.

## Features

### Pros

- Decoding for all kinds of video format that FFMpeg supports.
- For all client devices that support HTML5.
- Fast and real-time decoding without using cache, thus little loads for disk.
- Support for multiple audio tracks and subtile tracks.
- Support for multiple resolutions.

### Cons

- Resources Consuming (since it is real-time decoding and no cache is used)
- A few videos may not be streamed smoothly. (since the inaccuracy seek for FFMpeg).

## Requirement

- PHP
- FFMpeg with h264 support

## Usage

The following URL will output the m3u8 file for playing.

    m3u8.php?src=<path-to-video-file>&quality=<quality>

1. `<path-to-video-file>` must be an absolute URL relative to your domain (start with '/') when accessing resources in the same domain.
2. For `<quality>` option, please refer to [FFMpeg Video Size](https://ffmpeg.org/ffmpeg-all.html#Video-size).

### Config

See libs/config.php. You may need to change paths for `$ffmpeg` and `$ffmprob`.

## Example

Here is an example using video-js with hls plugin:

    demo.html?src=/Sample_video.rmvb

where `Sample_video.rmvb` located in `http(s)://<your-domain>/Sample_video.rmvb`.
