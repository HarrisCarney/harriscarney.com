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

      <div class="mobile__navigation">
				<img src="~/assets/images/menu.svg" width="20">
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
  display: flex;
  background: white;
  align-items: flex-end;
  z-index: 999;
}

.mobile__navigation {
  height: 20px;
  display: none;
  cursor: pointer;
}

.logo {
  width: 50px;
}

.header {
  height: 80px;
  display: flex;
  width: 100%;
  align-items: center;
  display: grid;
  grid-template-columns: minmax(300px, 1fr) minmax(50px, 350px);
}

.header .logoContainer {
  flex: 1;
}

.header .navigation {
  grid-column: 2;
  display: flex;
  flex: 1;
  height: 100%;
  align-self: flex-end;
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
    grid-template-columns: 1fr 1fr 1fr;
    grid-template-rows: 1fr 1fr;
  }

  .logoContainer {
    grid-column: 2;
    display: flex;
    justify-content: center;
  }

  .header .mobile__navigation {
    display: flex;
    justify-content: flex-end;
    grid-column: 3;
  }

  .header .navigation {
    display: none;
    grid-row: 2;
    grid-column: 1 / -1;
    width: 100%;
    padding: 20px 0;
    min-height: 220px;
    background: black;
    flex-direction: column;
    color: white;
  }

  .header .navigation a {
    color: white;
  }
}
</style>
