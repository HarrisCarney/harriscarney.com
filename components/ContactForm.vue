<template>
  <div class="formContainer">
    <div class="infoBox">
      <Logo class="what" />
      <h2 class="contactTagline">Like What You See?</h2>
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
  width: 60%;
  justify-content: space-around;
}

form {
  box-sizing: border-box;
  display: flex;
  align-items: center;
}

.testContainer {
  display: flex;
  flex-direction: column;
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
}

.what {
  transform: rotate(-90deg);
}

.submit {
  border-radius: 100%;
  width: 60px;
  height: 60px;
  background: var(--accent-color);
}

.contactTagline {
  color: var(--accent-color);
  letter-spacing: 0.08em;
  text-transform: uppercase;
  margin: 0;
  transform-origin: 0 0;
  writing-mode: vertical-rl;
  transform: rotate(180deg);
  transform-origin: 50% 50%;
}

.infoBox {
  display: flex;
  flex-direction: row;
  align-items: center;
}
</style>
