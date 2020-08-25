<template>
  <div class="footer">
    <Logo class="footer__logo" />

    <p class="footer__copyright">Copyright © 2020 Harris Carney</p>

    <div class="footer__socials">
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
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  font-size: 14px;
  align-items: center;
  justify-content: space-between;
}

.footer__logo {
  width: 40px;
  grid-column: 1;
}

.footer__copyright {
  grid-column: 2;
  text-align: center;
}

.footer__socials {
  grid-column: 3;
  width: 200px;
  display: flex;
  justify-self: flex-end;
  justify-content: space-between;
}

@media only screen and (max-width: 800px) {
  .footer {
    height: 180px;
    padding: 20px;
    grid-template-columns: 1fr;
    grid-template-rows: 1fr 1fr 1fr;
    justify-content: center;
  }

  .footer__logo {
    grid-column: 1;
    grid-row: 1;
    justify-self: center;
  }

  .footer__copyright {
    grid-column: 1;
    grid-row: 2;
    justify-self: center;
  }
  .footer__socials {
    grid-column: 1;
    grid-row: 3;
    justify-self: center;
  }
}
</style>
