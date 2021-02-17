<template>
  <div class="container">
    <canvas id="canvas"></canvas>

    <div class="landing">
      <div class="landing__info">
        <div class="info__titles">
          <h2 class="titles__sub" data-aos="fade-right">Harris Carney</h2>
          <h1 class="titles__main" data-aos="fade-right">Web Developer</h1>
        </div>
        <p class="info__description" data-aos="fade-right">
          Our interaction with the digital world has the ability to shape our
          views, trigger our emotions, and command our attention. My passion is
          bringing these ideas, feelings, and thoughts to fruition through good
          design and functional development.
        </p>
        <div class="info__action" data-aos="fade-right">
          <a href="#contactForm">Contact Me <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="icon-arrow" viewBox="0 0 16 16">
            <path fill-rule="evenodd" d="M4 8a.5.5 0 0 1 .5-.5h5.793L8.146 5.354a.5.5 0 1 1 .708-.708l3 3a.5.5 0 0 1 0 .708l-3 3a.5.5 0 0 1-.708-.708L10.293 8.5H4.5A.5.5 0 0 1 4 8z"/>
          </svg></a>
        </div>
      </div>

      <div class="landing__profile" data-aos="fade-left">
        <div class="profile__image">
          <img src="~assets/images/harris.png" />
        </div>
      </div>
    </div>

    <div id="work" class="works">
      <WorkItem
        number="01"
        title="BLK Fox Creative"
        subtitle="Freelance"
        description="This is a portfolio website that I built for an aspirting young graphic designer. She provided me with a custom photoshop design and from there I created the website in vanilla HTML, CSS, and JS."
        link="https://blkfoxcreative.com"
        image="blkfoxcreative-new.png"
        text-color="#F04E36"
      />
      <WorkItem
        number="02"
        title="TexasFITT Fitness Center"
        subtitle="Employed"
        description="TexasFITT is a health and wellness center located in Arlington, Texas with a strong focus on their community and a passion for spreading love for fitness. This is built in Wordpress to make it more useable for my client’s."
        link="https://texasfitt.com"
        image="texasfitt-new.png"
        text-color="#25C106"
      />
      <WorkItem
        number="03"
        title="The Amazing Spider-Man"
        subtitle="Project"
        description="I absolutely love the game, The Amazing Spiderman. After looking at Insomniac Game’s rather lacking website, I decided to redesign and build one myself.  This website is built in vanilla HTML, CSS, and JS."
        link="https://spiderman.harriscarney.com"
        image="spiderman-new.png"
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
  },

  mounted() {
    // CUSTOM CODE FOR BACKGROUND CANVAS CAN BE FOUND AT https://codepen.io/HarrisCarney/pen/EKxrgN
    // Canvas with Retina Support Boilerplate
    var canvasWidth, canvasHeight;

    var canvas = document.getElementById('canvas');
    var context = canvas.getContext('2d');

    var canvasSize = (canvas, context) => {
      canvas.width = window.innerWidth;
      canvas.height = window.innerHeight;

      var devicePixelRatio = window.devicePixelRatio || 1;
      var backingStoreRatio = context.webkitBackingStorePixelRatio || context.mozBackingStorePixelRatio || context.msBackingStorePixelRatio || context.oBackingStorePixelRatio || context.backingStoreRatio || 1;
      var ratio = devicePixelRatio / backingStoreRatio;

      if (devicePixelRatio !== backingStoreRatio) {
        var oldWidth = canvas.width;
        var oldHeight = canvas.height;

        canvasWidth = oldWidth;
        canvasHeight = oldHeight;

        canvas.width = Math.round(oldWidth * ratio);
        canvas.height = Math.round(oldHeight * ratio);

        canvas.style.width = oldWidth + 'px';
        canvas.style.height = oldHeight + 'px';
      }

      context.scale(ratio, ratio);
    }

    var collector = [];
    var amount = 50;

    var colors = ['rgba(255, 255, 255, 0.1)'];

    function particle() {
      this.size = Math.round(Math.random() * (4 - 2) + 2);
      this.lineSize = 0.8;
      this.connectDistance = 100;

      this.color = colors[Math.round(Math.random() * (colors.length - 1))];

      this.x = Math.round(Math.random() * canvasWidth);
      this.y = Math.round(Math.random() * canvasHeight);

      this.speed = 0.2;

      this.velocity = {
        x: (Math.random() > 0.5 ? 1 : -1),
        y: (Math.random() > 0.5 ? 1 : -1),
      };
    };

    particle.prototype = {
      update: function() {
        this.x += (this.velocity.x * this.speed);
        this.y += (this.velocity.y * this.speed);

        this.padding = 2;

        if (this.x < -this.padding) {
          this.velocity.x = -this.velocity.x;
        }

        if (this.x > canvasWidth + this.padding) {
          this.velocity.x = -this.velocity.x;
        }

        if (this.y < -this.padding) {
          this.velocity.y = -this.velocity.y;
        }

        if (this.y > canvasHeight + this.padding) {
          this.velocity.y = -this.velocity.y;
        }
      },

      draw: function() {
        context.fillStyle = this.color;
        context.beginPath();
        context.arc(this.x, this.y, this.size, 0, Math.PI * 2, false);
        context.fill();
      },

      connect: function() {
        context.lineWidth = this.lineSize;

        for (var p = 0; p < collector.length - 1; p++) {
          var p2 = collector[p];

          if(this !== p2) {
            var dist = Math.sqrt(Math.pow(this.x - p2.x, 2) + Math.pow(this.y - p2.y, 2));

            if (dist < this.connectDistance) {
              var gradient = context.createLinearGradient(this.x, this.y, p2.x, p2.y);
              gradient.addColorStop(0, this.color);
              gradient.addColorStop(1, p2.color);
              context.strokeStyle = gradient;

              context.beginPath();
              context.moveTo(this.x, this.y);
              context.lineTo(p2.x, p2.y);

              context.stroke();
            }
            context.closePath();
          }
        }
      }
    };

    function tick() {
      context.clearRect(0, 0, canvasWidth, canvasHeight);

      for (var x = collector.length; x < amount; x++) {
        collector.push(new particle());
      }

      collector.forEach(function(particle) {
        particle.update();
        particle.draw();
        particle.connect();
      });

      requestAnimationFrame(tick);
    }

    canvasSize(canvas, context);
    tick();

    window.addEventListener('resize', function() {
      canvasSize(canvas, context);
    });
  }
}
</script>

<style>
:root {
  --accent-color: #021243;
  --dark-accent: #0a61cd;
  --blkfox-orange: #f04e36;
  --spiderman-red: #df1f2d;
  --texasfitt-green: #25c106;
}

#canvas {
  position: absolute;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
}

.landing {
  display: flex;
  align-items: center;
  min-height: calc(100vh - 100px);
  width: 100%;
  justify-content: space-between;
  padding: 0 80px;
  background: #00071C;
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
  font-size: 1.5em;
  font-weight: 500;
  letter-spacing: 2px;
  color: white;
}

.titles__main {
  font-size: 4em;
  font-weight: 600;
  letter-spacing: 3px;
  margin: 12px 0 0px 0px;
  padding: 0;
  color: white;
}

.info__description {
  margin: 20px 0 20px 0;
  width: 80%;
  max-width: 700px;
  font-size: 14px;
  line-height: 36px;
  letter-spacing: 0.06em;
  color: white;
}

.info__description > span {
  color: var(--accent-color);
}

.info__action {
  width: 260px;
  height: 48px;
  margin: 0 0 40px 0;
  border-radius: 25px;
  border: 1px solid white;
  display: flex;
  justify-content: center;
  align-items: center;
}

.info__action > a {
  text-decoration: none;
  font-family: 'Sen';
  color: white;
  text-transform: uppercase;
  letter-spacing: 0.05em;
  font-size: 14px;
  display: flex;
  align-items: center;
}

.info__action > a > .icon-arrow {
  width: 24px;
  height: 24px;
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
  position: relative;
  order: 2;
  display: flex;
  align-items: flex-end;
}

.profile__image {
  width: 80%;
  padding: 80px 0 0 0;
  background: #021243;
  display: flex;
  margin: 0 auto;
  justify-content: center;
  align-items: flex-end;
  border-radius: 50%;
}

.profile__image > img {
  width: 45%;
  min-width: 100px;
  clip-path: circle(63%);
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
  padding: 80px 80px 0px 80px;
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
