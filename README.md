<!DOCTYPE html>
<html>
<head>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<style>
html, body {
  margin: 0;
  padding: 0;
  background: black;
  height: 100%;
}
video {
  width: 100%;
  height: 100%;
  object-fit: contain;
}
</style>
</head>
<body>

<video id="video" autoplay muted playsinline></video>

<script src="https://cdn.jsdelivr.net/npm/hls.js@latest"></script>
<script>
var video = document.getElementById('video');
var videoSrc = 'https://cctv.bandungkab.go.id/ed0b262d5dcdff42b65f0b036427cced/hls/dishub01/s0BPNnOcMS/s.m3u8';

if (Hls.isSupported()) {
  var hls = new Hls();
  hls.loadSource(videoSrc);
  hls.attachMedia(video);
} else if (video.canPlayType('application/vnd.apple.mpegurl')) {
  video.src = videoSrc;
}
</script>

</body>
</html>
