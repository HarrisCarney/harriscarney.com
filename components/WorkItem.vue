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
  margin: 100px 0;
  justify-content: space-between;
}

.itemDetailsContainer {
  display: flex;
  width: 100%;
  flex-direction: row !important;
  justify-content: space-between;
}

.bigAssNumber {
  font-size: 30px;
  margin-bottom: 40px;
  color: #afafaf;
  letter-spacing: 0.05em;
}

.bigAssNumber:before {
  content: '';
  display: inline-block;
  margin-right: 14px;
  width: 24px;
  height: 2px;
  background: #afafaf;
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
  width: 450px;
  font-size: 3em;
  letter-spacing: 0.05em;
}

.itemDetails__description {
  font-weight: normal;
  max-width: 500px;
  font-size: 14px;
  line-height: 36px;
  letter-spacing: 0.06em;
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
  justify-content: space-between;
  letter-spacing: 0.05em;
  font-size: 14px;
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
