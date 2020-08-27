<template>
  <div class="headerContainer">
    <div class="header">
      <div class="logoContainer">
        <a href="/"><Logo class="logo"/></a>
      </div>

      <div class="navigation">
        <NuxtLink to="/" class="link">Home</NuxtLink>
        <NuxtLink to="resume" class="link">Resume</NuxtLink>
        <NuxtLink to="#work" class="link">Work</NuxtLink>
        <NuxtLink to="#contactForm" class="link">Contact</NuxtLink>
      </div>

      <div class="mobile__navigation" v-on:click="mobileNav">
        <img src="~/assets/images/menu.svg" width="20" />
      </div>
    </div>
  </div>
</template>

<script>
import Logo from '~/components/Logo.vue';

export default {
  components: {
    Logo
  },
  methods: {
    getStyle(query, name) {
      var element = document.querySelector(query);
      return element.currentStyle
        ? element.currentStyle[name]
        : window.getComputedStyle
        ? window.getComputedStyle(element, null).getPropertyValue(name)
        : null;
    },
    mobileNav(e) {
      if (this.getStyle(".navigation", "display") === "none") {
        document.querySelector('.navigation').style.display = "flex";
      } else {
        document.querySelector('.navigation').style.display = "none";
      }
    }
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
  width: 20px;
  justify-self: end;
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
    grid-template-rows: 80px 1fr;
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
    grid-column: 1 / -1 !important;
    background: black;
    flex-direction: column;
    max-width: 100%;
  }

  .header .navigation a {
    color: white;
    height: 60px;
    line-height: 60px;
  }
}
</style>
