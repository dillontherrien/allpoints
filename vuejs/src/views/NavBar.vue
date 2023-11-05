<script setup lang="ts">
import { RouterLink } from 'vue-router'
</script>

<template>
  <header>
    <div class="header">
      <img alt="AllPoints logo" class="logo" src="@/assets/logo.png" />
      <div class="menu-icon"><font-awesome-icon icon="fa-solid fa-bars" size="2xl" /></div>

      <nav class="nav">
        <RouterLink class="nav-item" to="/home">Home</RouterLink>
        <RouterLink class="nav-item" to="/about">About Us</RouterLink>
        <RouterLink class="nav-item" to="#">Our Services</RouterLink>
        <RouterLink class="nav-item" to="/about">Contact Us</RouterLink>
      </nav>
    </div>
    <!-- <video autoplay="" muted="" loop=""><source src="https://www.cageapp.com/public-cdn/site/production/assets/f40af30b6264395dee8a756b76bae75ca2e5d4ab/videos/cage-hero_background-1.mp4" type="video/mp4"></video> -->
  </header>
  <RouterView/>
</template>

<style scoped>
.header {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
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
  padding-top: 10px;
  font-size: 18px;
  display: flex;
  justify-content: center;
  align-items: center;
  color: white;
  text-align: center;
  height: 100%;
}

.nav-item:hover{
    color: rgb(173, 173, 173);
}

.nav-item:active{
    color: rgb(173, 173, 173);
}

.logo {
  max-width: 250px;
}

/* Styles for larger screens */
.menu-icon {
  display: none; /* Hide the menu icon by default on larger screens */
}

/* Styles for phone resolutions */
@media (max-width: 767px) {
  .menu-icon {
    color: white;
    display: flex; /* Show the menu icon on phone resolutions */
    align-items: center;
    cursor: pointer; /* Add a cursor pointer for interaction */
    justify-content: center;
    width: 40px;
    transition: background-color 0.3s;
  }
  .logo {
    max-width: 150px;
  }
  .nav {
    display: none;
  }
}
</style>
