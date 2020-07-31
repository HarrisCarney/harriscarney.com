<template>
  <div id="contactForm" class="formContainer">
    <div class="infoBox">
      <h2 class="contactTagline">Let's have a friendly chat!</h2>
      <p>Don't like forms? <a href="#">Shoot me an email!</a></p>
    </div>
    <form action="">
      <div class="testContainer">
        <label for="name">Name</label>
        <input type="text" name="name" />
        <label for="email">Email</label>
        <input type="text" name="email" />
        <label for="message">Message</label>
        <input type="textbox" name="message" />
      </div>
      <input type="submit" class="submit" />
    </form>
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
.formContainer {
  display: flex;
  width: 100%;
  flex-direction: row;
  align-items: flex-start;
  justify-content: space-between;
  padding: 0 80px;
  margin: 40px 0;
}

.testContainer {
  display: flex;
  flex-direction: column;
}

form {
  width: 500px;
}

input {
  border-radius: 4px;
  background: #f6f6f6;
  border: none;
  height: 40px;
  width: 300px;
  margin: 5px;
  padding-left: 10px;
  font-size: 14px;
}

label {
  text-transform: uppercase;
  letter-spacing: 0.08em;
  font-weight: bold;
  font-size: 12px;
  margin-top: 20px;
}

.submit {
  background: white;
  width: 260px;
  height: 48px;
  margin: 20px 0 40px 0;
  border-radius: 4px;
  border: 1px solid var(--accent-color);
  display: flex;
  justify-content: center;
  align-items: center;
  cursor: pointer;
  text-decoration: none;
  font-family: 'Sen';
  text-transform: uppercase;
  align-items: center;
  letter-spacing: 0.05em;
  font-size: 14px;
  color: var(--accent-color);
}

.contactTagline {
  color: #333;
  letter-spacing: 0.08em;
  font-size: 50px;
  text-transform: uppercase;
  margin: 0 0 20px 0;
  width: 250px;
  padding: 0;
}

.infoBox {
  display: flex;
  flex-direction: column;
}

@media only screen and (max-width: 800px) {
  .formContainer {
    width: 100%;
    padding: 0 40px;
    flex-direction: column;
  }
}
</style>
