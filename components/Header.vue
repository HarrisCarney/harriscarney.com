<template>
  <div class="headerContainer">
    <div class="header">
      <div class="logoContainer">
        <a href="/"><Logo class="logo"/></a>
      </div>

      <div class="navigation">
        <NuxtLink to="/" class="link">Home</NuxtLink>
        <NuxtLink to="/resume" class="link">Resume</NuxtLink>
        <NuxtLink to="/work" class="link">Work</NuxtLink>
        <NuxtLink to="/contact" class="link">Contact</NuxtLink>
      </div>
    </div>
  </div>
</template>

<script>
import Logo from '~/components/Logo.vue'

export default {
  components: {
    Logo
  }
}
</script>
<style>
.headerContainer {
  position: fixed;
  top: 0;
  height: 100px;
  width: 100vw;
  padding: 0 80px;
  background: white;
  display: flex;
  align-items: flex-end;
  z-index: 999;
}

.logo {
  width: 50px;
}

.header {
  height: 80px;
  display: flex;
  width: 100%;
  align-items: center;
}

.header .logoContainer {
  flex: 1;
}

.header .logoContainer .logo {
}

.header .navigation {
  display: flex;
  flex: 1;
  height: 100%;
  align-items: center;
  justify-content: space-around;
  max-width: 500px;
}

.header .navigation a {
  text-decoration: none;
  color: #333;
  font-weight: bold;
  font-size: 14px;
}

.header .navigation a:hover {
  color: var(--accent-color);
}
</style>
