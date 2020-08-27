<template>
  <div id="contactForm" class="form__container">
    <div class="form__info">
      <h2 class="form__tagline">Let's have a <br> friendly chat!</h2>
      <p>
        Don't like forms? Email me!  
        <a href="mailto:me@harriscarney.com" class="form__email"><img src="~/assets/images/email.svg" alt="">me@harriscarney.com</a>
      </p>
    </div>
    <form
      action="https://formsubmit.io/send/3902f58a-9ecb-4708-b35f-ea5b1e2f130c"
      method="post"
    >
      <div class="input__container">
        <input name="_formsubmit_id" type="text" style="display:none" />
        <input name="_redirect" type="hidden" id="name" value="https://harriscarney.com/">
        <div class="input__row">
          <div class="input__item input__item--small">
            <label for="name">Name</label>
            <input type="text" name="name" class="input" /> 
          </div>
          <div class="input__item input__item--small">
            <label for="email">Email</label>
            <input type="text" name="email" class="input" />
          </div>
        </div>
        <div class="input__row">
          <div class="input__item">
            <label for="message">Message</label>
            <textarea type="textbox" name="message" rows="4" class="message"/>
          </div>
        </div>
      </div>
      <input type="submit" class="submit" />
    </form>
  </div>
</template>

<style>
.form__container {
  position: relative;
  display: flex;
  width: 100%;
  flex-direction: row;
  align-items: flex-start;
  justify-content: space-between;
  padding: 0 80px;
  margin: 40px 0 120px 0;
}

.input__container {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.input__row {
  display: flex;
  justify-content: space-between;
}

.input__item {
  display: flex;
  width: 100%;
  flex-direction: column;
  margin-bottom: 20px;
}

.input__item--small {
  width: 49%;
}

.form__info {
  flex: 1;
}

form {
  flex: 1;
  width: 100%;
}

.input {
  border-radius: 4px;
  background: #f6f6f6;
  border: none;
  height: 40px;
  margin: 5px 0 0 0;
  padding-left: 10px;
  font-size: 14px;
}

.message {
  border-radius: 4px;
  background: #f6f6f6;
  border: none;
  width: 100%;
  margin: 5px 0 0 0;
  padding: 10px;
  font-size: 14px;
  resize: none;
}

label {
  text-transform: uppercase;
  letter-spacing: 0.08em;
  font-weight: bold;
  font-size: 14px;
}

.submit {
  background: white;
  width: 100%;
  height: 48px;
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

.submit:hover {
  background: var(--accent-color);
  color: white;
}

.form__tagline {
  color: #333;
  letter-spacing: 0.08em;
  font-size: 40px;
  text-transform: uppercase;
  margin: 0 0 20px 0;
  padding: 0;
}

.form__email {
  margin-top: 40px;
  text-decoration: none;
  color: var(--accent-color);
  display: flex;
}

.form__email > img {
  margin-right: 12px;
}

.form__info {
  display: flex;
  flex-direction: column;
}

@media only screen and (max-width: 800px) {
  .form__tagline {
    font-size: 35px;
  }

  .form__container {
    width: 100%;
    padding: 0 40px;
    flex-direction: column;
    margin-bottom: 60px;
  }

  .input__container {
    margin-top: 40px;
  }

  .input__row {
    flex-direction: column;
  }

  .input__item--small {
    width: 100%;
  }
}
</style>
