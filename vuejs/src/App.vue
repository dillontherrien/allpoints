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
        <RouterLink class="nav-item white" to="/about">About Us</RouterLink>
        <RouterLink class="nav-item white" to="/services">Our Services</RouterLink>
        <RouterLink class="nav-item white" to="/contact">Contact Us</RouterLink>
      </nav>
    </div>
    <!-- <video autoplay="" muted="" loop=""><source src="https://www.cageapp.com/public-cdn/site/production/assets/f40af30b6264395dee8a756b76bae75ca2e5d4ab/videos/cage-hero_background-1.mp4" type="video/mp4"></video> -->
  </header>
  <div class="background-video">
    <div class="overlay"></div>
    <video autoplay muted loop>
      <source
        src="https://www.cageapp.com/public-cdn/site/production/assets/f40af30b6264395dee8a756b76bae75ca2e5d4ab/videos/cage-hero_background-1.mp4"
        type="video/mp4"
      />
    </video>

    <div class="text-overlay">
      <h1>Put down the rake.</h1>
      <p>Let us do the hard work for you.</p>
    </div>
  </div>

  <div class="content">
    <h1>Welcome to My Website</h1>
    <p>This is some sample content.</p>
    <button>Click me</button>
  </div>
</template>

<style scoped>
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
  background-color: rgb(250, 249, 250);
  height: 100vh;
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
