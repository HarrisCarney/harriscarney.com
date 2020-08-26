<template>
  <div class="container">
    <div class="landing">
      <div class="landing__info">
        <div class="info__titles">
          <h2 class="titles__sub">Front End Developer & Designer</h2>
          <h1 class="titles__main">Harris Carney</h1>
        </div>
        <p class="info__description">
          Our interaction with the digital world has the ability to shape our
          views, trigger our emotions, and command our attention. My passion is
          bringing these ideas, feelings, and thoughts to fruition through good
          design and functional development.
        </p>
        <div class="info__action">
          <a href="#contactForm">Contact Me</a>
        </div>
        <div class="info__socials">
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

      <div class="landing__profile">
        <div class="profile__image">
          <img src="~assets/images/harris.png" />
        </div>
        <div class="profile__textbar">
          <h2>My Work</h2>
          <img src="~assets/images/downArrow.svg" width="18" />
        </div>
      </div>
    </div>

    <div id="work" class="works">
      <h1>DESIGN. CREATE. BUILD.</h1>
      <WorkItem
        number="01"
        title="BLK Fox Creative"
        subtitle="Freelance"
        description="This is a portfolio website that I build for an aspirting young graphic designer. She provided me with a custom photoshop design and from there I build the website in vanilla HTML, CSS, and JS."
        link="https://blkfoxcreative.com"
        image="blkfoxcreative.png"
        text-color="#F04E36"
      />
      <WorkItem
        number="02"
        title="TexasFITT Fitness Center"
        subtitle="Employed"
        description="TexasFITT is a health and wellness center located in Arlington, Texas with a strong focus on their community and a passion for spreading love for fitness. This is built in Wordpress to make it more useable for my client’s."
        link="https://texasfitt.com"
        image="texasfitt.png"
        text-color="#25C106"
      />
      <WorkItem
        number="03"
        title="The Amazing Spider-Man"
        subtitle="Project"
        description="I absolutely love the game, The Amazing Spiderman. After looking at Insomniac Game’s rather lacking website, I decided to redesign and build one myself.  This website is built in vanilla HTML, CSS, and JS."
        link="https://blkfoxcreative.com"
        image="spiderman.png"
        text-color="#DF1F2D"
      />
    </div>
    <ContactForm />
  </div>
</template>

<script>
import WorkItem from '~/components/WorkItem.vue'
import ContactForm from '~/components/ContactForm.vue'

export default {
  components: {
    WorkItem,
    ContactForm
  },
  data() {
    return {
      title: 'Harris Carney | Developer & Designer'
    }
  },
  head() {
    return {
      title: this.title
    }
  }
}
</script>

<style>
:root {
  --accent-color: #1875ff;
  --dark-accent: #0a61cd;
  --blkfox-orange: #f04e36;
  --spiderman-red: #df1f2d;
  --texasfitt-green: #25c106;
}

.landing {
  display: flex;
  align-items: center;
  min-height: 100vh;
  width: 100%;
  justify-content: space-between;
  padding: 0 80px;
}

.landing__info {
  display: flex;
  order: 1;
  flex-direction: column;
  justify-content: center;
}

.info__titles {
  position: relative;
  margin: 10px 0 0 0;
  font-size: 16px;
}

.titles__sub {
  font-size: 1em;
  font-weight: normal;
  letter-spacing: 2px;
  color: var(--accent-color);
}

.titles__main {
  font-size: 3em;
  margin: 12px 0 0px 0px;
  padding: 0;
}

.info__description {
  margin: 20px 0 20px 0;
  width: 80%;
  max-width: 700px;
  font-size: 14px;
  line-height: 36px;
  letter-spacing: 0.06em;
}

.info__description > span {
  color: var(--accent-color);
}

.info__action {
  width: 260px;
  height: 48px;
  margin: 0 0 40px 0;
  border-radius: 4px;
  border: 1px solid var(--accent-color);
  display: flex;
  justify-content: center;
  align-items: center;
}

.info__action > a {
  text-decoration: none;
  font-family: 'Sen';
  color: var(--accent-color);
  text-transform: uppercase;
  letter-spacing: 0.05em;
  font-size: 14px;
}

.info__action:hover {
  background: var(--accent-color);
}

.info__action:hover a {
  color: white;
}

.info__socials {
  display: flex;
  width: 200px;
  justify-content: space-between;
  align-items: center;
}

.landing__profile {
  width: 40%;
  order: 2;
  display: flex;
  align-items: flex-end;
}

.profile__image {
  width: 100%;
  padding: 80px 0 0 0;
  background: var(--accent-color);
  display: flex;
  justify-content: center;
  align-items: flex-end;
}

.profile__image > img {
  width: 40%;
  min-width: 100px;
}

.profile__textbar {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-left: 20px;
}

.profile__textbar > h2 {
  text-transform: uppercase;
  writing-mode: vertical-rl;
  font-size: 16px;
  margin: 10px 0;
}

.works {
  width: 100%;
  padding: 0 80px;
  flex-direction: column;
}

.works > h1 {
  font-family: 'Sen';
  font-size: 20px;
  margin-bottom: 80px;
  font-weight: bold;
  letter-spacing: 0.25em;
}

@media only screen and (max-width: 800px) {
  .landing {
    flex-direction: column;
    align-items: flex-start;
    margin: 0;
    padding: 0 40px;
  }

  .info__titles {
    margin-top: 40px;
    font-size: 14px;
  }

  .info__description {
    width: 100%;
  }

  .info__action {
    width: 100%;
  }

  .landing__profile {
    order: 1;
    width: 100%;
  }

  .landing__info {
    order: 2;
  }

  .profile__textbar {
    display: none;
  }

  .works {
    margin-top: 40px;
    padding: 0 40px;
  }
}
</style>
