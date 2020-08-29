<template>
  <div class="thanks">
    <h1>Thanks for your submission!</h1>
    <h2>We'll be in contact shortly!</h2>
    <a href="/">Return to home page.</a>
  </div>
</template>


<script>
export default {
  data() {
    return {
      title: 'Harris Carney | Thanks for your submission!'
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
  .thanks {
    width: 100vw;
    height: calc(100vh - 100px);
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }

  .thanks > h1 {
    font-size: 8vw;
    text-align: center;
    margin: 0;
    color: var(--accent-color);
  }

  .thanks > h2 {
    margin: 20px;
    font-size: 2vw;
    color: #333;
  }

  .thanks > a {
    color: var(--accent-color);
  }
</style>