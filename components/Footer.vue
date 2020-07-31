<template>
  <div class="footer">
    <Logo class="footerLogo" />
    <p>Copyright © 2020 Harris Carney</p>
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
  font-size: 14px;
  align-items: center;
  justify-content: space-between;
}

.footerLogo {
  width: 40px;
  justify-self: flex-start;
}

.footer p {
  position: relative;
  text-align: center;
  margin: 0 auto;
}

.footerSocial {
  width: 200px;
  display: flex;
  justify-self: flex-end;
  justify-content: space-between;
}

@media only screen and (max-width: 800px) {
  .footer {
    height: 180px;
    flex-direction: column;
    justify-content: space-around;
  }
}
</style>
