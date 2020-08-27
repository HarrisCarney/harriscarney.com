<template>
  <div class="pdf">
    <pdf src="/resume.pdf" />
  </div>
</template>

<script>
import pdf from 'vue-pdf';
 
export default {
  components: {
    pdf
  },
  data() {
    return {
      title: 'Harris Carney | Resume'
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
  .pdf {
    margin: 40px auto;
    width: 100%;
    display: flex;
    justify-content: center;
  }

  .pdf > * {
    width: 60%;
  }

  @media only screen and (max-width: 800px) {
    .pdf > * {
      width: 100%;
    }
  }
</style>