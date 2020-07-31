<template>
  <div class="headerContainer">
    <div class="header">
      <div class="logoContainer">
        <a href="/"><Logo class="logo"/></a>
      </div>

      <div class="navigation">
        <NuxtLink to="/" class="link">Home</NuxtLink>
        <NuxtLink to="/resume" class="link">Resume</NuxtLink>
        <NuxtLink to="#work" class="link">Work</NuxtLink>
        <NuxtLink to="#contactForm" class="link">Contact</NuxtLink>
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
  position: sticky;
  top: 0;
  height: 100px;
  width: 100vw;
  padding: 0 80px;
  background: white;
  display: flex;
  align-items: flex-end;
  z-index: 999;
}

.mobile--navigation {
  height: 50px;
  display: flex;
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

.header .navigation {
  display: flex;
  flex: 1;
  height: 100%;
  align-items: center;
  justify-content: space-between;
  max-width: 350px;
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

@media only screen and (max-width: 800px) {
  .headerContainer {
    padding: 0 40px;
  }
  
  .header {
    width: 100vw;
    flex-direction: column;
  }

  .header .navigation {
    display: none;
    min-height: 200px;
    width: 100%;
    padding: 20px 0px;
    background: black;
    flex-direction: column;
    color: white;
  }

  .header .navigation a {
    color: white;
  }
}
</style>
