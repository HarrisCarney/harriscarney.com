<template>
  <div class="footer">
    <Logo class="footerLogo" />
    <p>Copyright 2020</p>
    <div class="footerSocial">
      <a href="https://codepen.io/harriscarney" target="_">
        <img src="~assets/images/codepen.svg" width="16" />
      </a>
      <a href="#" target="_">
        <img src="~assets/images/linkedin.svg" width="16" />
      </a>
      <a href="https://github.com/harriscarney" target="_">
        <img src="~assets/images/github.svg" width="16" />
      </a>
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
.footer {
  width: 100vw;
  height: 80px;
  background: #f3f3f3;
  padding: 0 80px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.footerLogo {
  width: 40px;
}

.footerSocial {
  width: 200px;
  display: flex;
  justify-content: space-between;
}
</style>
