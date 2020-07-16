<template>
  <div class="itemContainer">
    <div class="bigAssNumber">{{ number }}.</div>
    <div class="itemDetailsContainer">
      <div class="itemDetails">
        <div class="itemDetails__subtitle" :style="{ color: textColor }">
          {{ subtitle }}
        </div>
        <div class="itemDetails__title">{{ title }}</div>
        <div class="itemDetails__description">{{ description }}</div>
        <div class="itemDetails__link" :style="{ borderColor: textColor }">
          <a :href="link" :style="{ color: textColor }">View Site</a>
        </div>
      </div>
      <div class="itemImage">
        <img :src="require(`@/assets/images/${image}`)" class="image" />
      </div>
    </div>
  </div>
</template>
<script>
export default {
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
  flex-direction: column;
  margin: 150px 0;
  justify-content: space-between;
}

.itemDetailsContainer {
  margin-top: 40px;
  display: flex;
  width: 100%;
  flex-direction: row !important;
  justify-content: space-between;
}

.bigAssNumber {
  font-size: 30px;
  color: #000;
}

.bigAssNumber:before {
  content: '';
  display: inline-block;
  margin-right: 20px;
  width: 30px;
  height: 1px;
  background: #000;
}

.itemDetails {
  position: relative;
  order: 1;
  display: flex;
  justify-content: center;
  flex-direction: column;
  font-size: 12px;
}

.itemDetails > * {
  margin: 10px 0 10px 0;
}

.itemImage {
  display: flex;
  align-items: center;
  order: 2;
}

.itemDetails__subtitle {
  font-size: 16px;
  font-weight: normal;
  letter-spacing: 1px;
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

.itemDetails__link {
  width: 260px;
  height: 48px;
  margin: 20px 0 40px 0;
  border-radius: 4px;
  border: 1px solid;
  display: flex;
  justify-content: center;
  align-items: center;
  cursor: pointer;
}

.itemDetails__link > a {
  text-decoration: none;
  text-transform: uppercase;
  display: flex;
  align-items: center;
  font-size: 1.1em;
  justify-content: space-between;
}

.image {
  width: 500px;
}

/* .itemContainer:nth-child(odd) .itemDetails {
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
} */

@media only screen and (max-width: 800px) {
  .itemContainer {
    flex-direction: column;
    width: 100vw;
  }

  .itemDetailsContainer {
    flex-direction: column !important;
  }

  .itemDetails {
    order: 2;
    max-width: 100%;
    margin: 20px 0 0 0;
  }

  .image {
    width: 300px;
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

  .bigAssNumber {
    top: -450px;
  }
}
</style>
