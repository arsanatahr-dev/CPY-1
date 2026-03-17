<!DOCTYPE html>
<html>
<head>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<style>
html, body {
  margin: 0;
  padding: 0;
  background: transparent;
  height: 100%;
  overflow: hidden;
}
.video-container {
  width: 100%;
  max-width: 480px;
  margin: auto;
}
video {
  width: 100%;
  height: auto;
  display: block;
}
</style>
</head>
<body>

<div class="video-container">
  <video id="video" autoplay muted playsinline></video>
</div>

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
