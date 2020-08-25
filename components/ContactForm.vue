<template>
  <div id="contactForm" class="form__container">
    <div class="form__info">
      <h2 class="form__tagline">Let's have a friendly chat!</h2>
      <p>
        Don't like forms?
        <a href="mailto:me@harriscarney.com">Shoot me an email!</a>
      </p>
    </div>
    <form
      action="https://formsubmit.io/send/3902f58a-9ecb-4708-b35f-ea5b1e2f130c"
      method="post"
    >
      <div class="input__container">
        <input name="_formsubmit_id" type="text" style="display:none" />
        <!-- <input name="_redirect" type="hidden" id="name" value="https://harriscarney.com/"> -->
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

<style>
.form__container {
  display: flex;
  width: 100%;
  flex-direction: column;
  align-items: flex-start;
  justify-content: space-between;
  padding: 0 80px;
  margin: 40px 0;
}

.input__container {
  display: flex;
  flex-direction: column;
}

.form__info {
  flex: 1;
}

form {
  flex: 1;
  width: 100%;
}

input {
  border-radius: 4px;
  background: #f6f6f6;
  border: none;
  height: 40px;
  width: 100%;
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
  width: 100%;
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

.form__tagline {
  color: #333;
  letter-spacing: 0.08em;
  font-size: 50px;
  text-transform: uppercase;
  margin: 0 0 20px 0;
  padding: 0;
}

.form__info {
  display: flex;
  flex-direction: column;
}

@media only screen and (max-width: 800px) {
  .form__container {
    width: 100%;
    padding: 0 40px;
    flex-direction: column;
  }
}
</style>
