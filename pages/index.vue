<template>
  <div class="container">
    <div class="landingDetails">
      <div class="detailsContainer">
        <div class="detailsTitles">
          <h2 class="detailsSubtitle">Front End Developer & Designer</h2>
          <h1 class="detailsTitle">Harris Carney</h1>
        </div>
        <p class="detailsDescription">
          Our interaction with the digital world has the ability to shape our
          views, trigger our emotions, and command our attention. My passion is
          bringing these ideas, feelings, and thoughts to fruition through good
          design and functional development.
        </p>
        <div class="detailsButton">
          <a href="#">Contact Me</a>
        </div>
        <div class="detailsSocial">
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
      <div class="landingImage">
        <div class="profilePicture">
          <img src="~assets/images/harris.png" />
        </div>
        <div class="textBar">
          <h2>My Work</h2>
          <img src="~assets/images/downArrow.svg" width="18" />
        </div>
      </div>
    </div>
    <div class="myWork">
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
  </div>
</template>

<script>
import WorkItem from '~/components/WorkItem.vue'

export default {
  components: {
    WorkItem
  },
  data() {
    return {
      title: 'Harris Carney | Web Developer & Designer'
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

.myWork {
  width: 100%;
  display: flex;
  margin-top: 40px;
  padding: 0 80px;
  flex-direction: column;
}

.myWork > h1 {
  font-family: 'Sen';
  font-size: 20px;
  font-weight: bold;
  letter-spacing: 0.25em;
}

.landingDetails {
  position: relative;
  top: 100px;
  display: flex;
  align-items: center;
  min-height: 100vh;
  width: 100%;
  order: 1;
  justify-content: space-between;
  padding: 80px;
}

.detailsContainer {
  display: flex;
  order: 1;
  height: 450px;
  flex-direction: column;
  justify-content: center;
}

.detailsTitle {
  position: relative;
  margin: 10px 0 0px 0;
  font-size: 3em;
  letter-spacing: 0.05em;
}

.detailsSubtitle {
  font-size: 16px;
  font-weight: normal;
  letter-spacing: 2px;
  color: var(--accent-color);
}

.detailsDescription {
  margin: 20px 0 20px 0;
  width: 80%;
  max-width: 700px;
  font-size: 14px;
  line-height: 36px;
  letter-spacing: 0.06em;
}

.detailsButton {
  width: 260px;
  height: 48px;
  margin: 0 0 40px 0;
  border-radius: 4px;
  border: 1px solid var(--accent-color);
  display: flex;
  justify-content: center;
  align-items: center;
}

.detailsButton > a {
  text-decoration: none;
  font-family: 'Sen';
  color: var(--accent-color);
  text-transform: uppercase;
  letter-spacing: 0.05em;
  font-size: 14px;
}

.detailsButton:hover {
  background: var(--accent-color);
}

.detailsButton:hover a {
  color: white;
}

.detailsDescription > span {
  color: var(--accent-color);
}

.detailsAction {
  width: 280px;
  height: 50px;
  border-radius: 4px;
  text-align: center;
  line-height: 50px;
  font-weight: bold;
  border: 1px solid var(--accent-color);
  cursor: pointer;
}

.detailsAction:hover {
  background: var(--accent-color);
}

.detailsAction:hover > a {
  color: #fff;
}

.detailsAction > a {
  text-decoration: none;
  color: var(--accent-color);
  font-weight: normal;
  font-size: 14px;
}

.detailsSocial {
  display: flex;
  width: 200px;
  justify-content: space-between;
  align-items: center;
}

.landingImage {
  width: 40%;
  order: 2;
  display: flex;
  align-items: flex-end;
}

.textBar {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.textBar > h2 {
  text-transform: uppercase;
  writing-mode: vertical-rl;
  font-size: 16px;
  margin: 10px 0;
}

.profilePicture {
  background: var(--accent-color);
}

.profilePicture > img {
  width: 100%;
}


@media only screen and (max-width: 800px) {
  .landingDetails {
    flex-direction: column;
    align-items: flex-start;
    margin: 0;
    padding: 0 40px;
  }
  .landingImage {
    order: 1;
    width: 100%;
  }
  .detailsContainer {
    order: 2;
  }

  .textBar {
    display: none;
  }

  .myWork {
    padding: 0 40px;
  }
}
</style>
