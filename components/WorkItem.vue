<template>
  <div class="itemContainer">
    <div class="itemDetails">
      <div class="bigAssNumber">{{ number }}</div>
      <div class="itemDetails__subtitle" :style="{ color: textColor }">
        {{ subtitle }}
      </div>
      <div class="itemDetails__title">{{ title }}</div>
      <div class="itemDetails__description">{{ description }}</div>
      <div class="itemDetails__link">
        <a :href="link" :style="{ color: textColor }">
          View Site
          <RightArrow :color="textColor" />
        </a>
      </div>
    </div>
    <div class="itemImage">
      <img :src="require(`@/assets/images/${image}`)" width="400" />
    </div>
  </div>
</template>
<script>
import RightArrow from '~/components/RightArrow.vue'

export default {
  components: {
    RightArrow
  },

  props: [
    'number',
    'title',
    'subtitle',
    'description',
    'link',
    'image',
    'textColor'
  ]
}
</script>
<style>
.itemContainer {
  position: relative;
  font-family: 'Sen';
  width: 100%;
  display: flex;
  align-items: center;
  margin: 100px 0;
  justify-content: space-around;
}

.bigAssNumber {
  position: absolute;
  top: -200px;
  font-size: 300px;
  z-index: -1;
  color: #f6f6f6;
}

.itemDetails {
  position: relative;
  order: 1;
  height: 360px;
  display: flex;
  flex-direction: column;
  font-size: 12px;
}

.itemDetails > * {
  margin: 10px 0 10px 0;
}

.itemImage {
  order: 2;
}

.itemDetails__subtitle {
  letter-spacing: 0.04em;
  font-size: 1.5em;
  text-transform: uppercase;
}

.itemDetails__title {
  font-weight: bold;
  letter-spacing: 0.04em;
  font-size: 50px;
  width: 450px;
}

.itemDetails__description {
  font-weight: normal;
  font-size: 1.4em;
  max-width: 500px;
  line-height: 200%;
}

.itemDetails__link > a {
  width: 100px;
  text-decoration: none;
  display: flex;
  align-items: center;
  font-size: 1.3em;
  justify-content: space-between;
}

.itemContainer:nth-child(odd) .itemDetails {
  order: 2;
  align-items: flex-end;
}

.itemContainer:nth-child(odd) .itemDetails > * {
  text-align: right;
}

.itemContainer:nth-child(even) .itemDetails > .bigAssNumber {
  left: -40px;
}

.itemContainer:nth-child(odd) .itemDetails > .bigAssNumber {
  right: -40px;
}

.itemContainer:nth-child(odd) .itemImage {
  order: 1;
}

@media only screen and (max-width: 800px) {
  .itemContainer {
    flex-direction: column;
  }

  .itemDetails {
    order: 2;
    max-width: 80%;
    margin: 20px 0 0 0;
  }

  .itemDetails {
    align-items: flex-start;
  }

  .itemDetails > * {
    text-align: left !important;
  }

  .itemImage {
    order: 1;
  }
}
</style>
