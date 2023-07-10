<script setup lang="ts"></script>

<template>
  <div class="background-video">
    <div class="overlay"></div>
    <video autoplay muted loop>
      <source
        src="https://www.cageapp.com/public-cdn/site/production/assets/f40af30b6264395dee8a756b76bae75ca2e5d4ab/videos/cage-hero_background-1.mp4"
        type="video/mp4"
      />
    </video>
  </div>

  <div class="content">
    <h1>Welcome to My Website</h1>
    <p>This is some sample content.</p>
    <button>Click me</button>
  </div>
</template>

<style scoped>
.background-video {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100vh;
  z-index: -1;
  overflow: hidden;
}

.background-video video {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
}

.content {
  margin-top: 100vh;
  background-color: white;
  height: 100vh;
  width: 100% !important;
}
</style>
