<script setup lang="ts">
import { RouterLink } from 'vue-router'
</script>

<template>
  <header>
    <div class="header">
      <router-link to="/" class="logo">
        <img alt="AllPoints logo" src="@/assets/logo.png" />
      </router-link>

      <div class="menu-icon"><font-awesome-icon icon="fa-solid fa-bars" size="2xl" /></div>

      <nav class="nav">
        <RouterLink class="nav-item white" to="/">Home</RouterLink>
        <RouterLink class="nav-item white" to="/services">Our Services</RouterLink>
        <RouterLink class="nav-item white" to="/about">About Us</RouterLink>
        <RouterLink class="nav-item white" to="/contact">Contact Us</RouterLink>
      </nav>
    </div>
    <!-- <video autoplay="" muted="" loop=""><source src="https://www.cageapp.com/public-cdn/site/production/assets/f40af30b6264395dee8a756b76bae75ca2e5d4ab/videos/cage-hero_background-1.mp4" type="video/mp4"></video> -->
  </header>
  <div class="background-video">
    <div class="overlay"></div>
    <video autoplay muted loop>
      <source src=".\assets\mow.mp4" type="video/mp4" />
    </video>

    <div class="text-overlay">
      <h1>Put down the rake.</h1>
      <p>Let us do the hard work for you.</p>
    </div>
  </div>

  <div class="content">
    <!-- <div class="title-text">Our Services</div> -->
    <div class="services">
      <div class="services-card">
        <img class="service-card-image" alt="image of service" src="@/assets/service2.png" />
        <div class="service-card-text">
            <div class="service-card-text-title">Plowing</div>
            <div class="service-card-text-content">Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</div>
        </div>
      </div>
      <div class="services-card">
        <img class="service-card-image" alt="image of service" src="@/assets/service2.png" />
        <div class="service-card-text">
            <div class="service-card-text-title">Landscaping</div>
            <div class="service-card-text-content">Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</div>
        </div>
      </div>
      <div class="services-card">
        <img class="service-card-image" alt="image of service" src="@/assets/service2.png" />
        <div class="service-card-text">
            <div class="service-card-text-title">Hardscaping</div>
            <div class="service-card-text-content">Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.title-text {
  color: #000;
  font-size: 2rem;
  text-align: center;
}
.services {
  padding-top: 1rem;
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  align-items: stretch;
  justify-content: center;
}

.services-card {
border: 1px solid #eee;
box-shadow: 0 2px 2px 0 rgba(0,0,0,0.05);
border-radius: 0.5em;
display: flex;
flex-direction: column;
margin-left: 1.5em;
margin-right: 1.5em;
margin-bottom: 2em;
}

.service-card-image {
 max-height: 55em;
 width: 100%;
 max-width: 360px;
 overflow: hidden;
 border-radius: 0.25em 0.25em 0 0;
 overflow-clip-margin: content-box;
}

.service-card-text {
    padding: 2em;
}

.service-card-text-title {
    font-size: 2em;
    color: #4c4c4c;
    margin: 0.3em 0;
}

.service-card-text-content {
    min-height: 4em;
    color: #4c4c4c;
    line-height: 1.33em;
    font-size: 1.33em;
    display: block;
    margin-block-start: 1em;
    margin-block-end: 1em;
    margin-inline-start: 0px;
    margin-inline-end: 0px;
    text-wrap: wrap;
    max-width: 290px;
}
.header {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  height: 70px;
  z-index: 2;
  text-align: center;
  width: 100%;
}

.nav {
  display: flex;
  width: 50%;
  justify-content: flex-end;
  align-content: center;
  align-items: stretch;
}

.nav-item {
  margin-left: 20px;
  margin-top: 13px;
  padding: 10px;
  padding-left: 15px;
  padding-right: 15px;
  font-size: 18px;
  display: flex;
  justify-content: center;
  align-items: center;
  text-transform: uppercase;
  text-align: center;
  height: 60%;
}

.white {
  color: white;
}

.white:hover {
  color: rgb(219, 219, 219);
}
.black {
  color: black;
}

.black:hover {
  color: rgb(107, 107, 107);
}

.logo {
  display: flex;
  align-items: center;
}

.logo img {
  max-width: 250px;
  max-height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
}

/* Styles for larger screens */
.menu-icon {
  display: none; /* Hide the menu icon by default on larger screens */
  margin-right: 1rem;
}

/* Styles for phone resolutions */
@media (max-width: 920px) {
  .menu-icon {
    color: white;
    display: flex; /* Show the menu icon on phone resolutions */
    align-items: center;
    cursor: pointer; /* Add a cursor pointer for interaction */
    justify-content: center;
    width: 40px;
    transition: background-color 0.3s;
  }

  .logo img {
    max-width: 150px;
    object-fit: contain;
  }
  .nav {
    display: none;
  }

  .services {
    padding-top: 0rem;
  }
  .services-card {
    flex-basis: 100%;
  }
}

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
  background-color: rgba(0, 0, 0, 0.75);
}

.text-overlay {
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  text-align: center;
  color: white;
  font-weight: bold;
  width: 85%;
  font-size: 2vh;
  opacity: 1;
  transition: opacity 0.5s;
}

.text-overlay.hidden {
  opacity: 0;
  pointer-events: none;
}
.content {
  margin-top: 100vh;
  background-color: rgb(255, 255, 255);
  /* height: 100%; */
  width: 100%;
  position: absolute;
  left: 0%;
  padding: 1rem;
}
</style>

<script lang="ts">
export default {
  data() {
    return {
      prevScrollPos: 0
    }
  },
  mounted() {
    window.addEventListener('scroll', this.handleScroll)
  },
  beforeUnmount() {
    window.removeEventListener('scroll', this.handleScroll)
  },
  methods: {
    handleScroll() {
      const textOverlay = document.querySelector('.text-overlay')

      if (textOverlay == null) {
        return
      }

      const currentScrollPos = window.pageYOffset

      if (currentScrollPos > this.prevScrollPos) {
        textOverlay.classList.add('hidden')
      } else {
        textOverlay.classList.remove('hidden')
      }

      this.prevScrollPos = currentScrollPos
    }
  }
}
</script>
