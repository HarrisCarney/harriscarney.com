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
  grid-column: 1;
}

.header {
  height: 80px;
  display: flex;
  width: 100%;
  align-items: center;
  margin-top: 20px;
  z-index: 1;
}

.header .logoContainer {
  flex: 1;
}

.header .logoContainer .logo {
  margin-left: 80px;
}

.header .navigation {
  display: flex;
  flex: 1;
  margin-right: 80px;
  height: 100%;
  align-items: center;
  justify-content: space-around;
  max-width: 500px;
}

.header .navigation a {
  text-decoration: none;
  color: #333;
  font-weight: normal;
  font-size: 14px;
}
</style>
