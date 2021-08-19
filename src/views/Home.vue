<template>
  <div class="home">
    <Productlistone></Productlistone>
    <Productlisttwo></Productlisttwo>
  </div>
</template>

<script>
import Productlistone from '../components/Productlistone.vue'
import Productlisttwo from '../components/Productlisttwo.vue'

export default {
  name: 'Home',

  components: {
    Productlistone,
    Productlisttwo
  },

  data() {
    return {
      
    }
  }
}
</script>

<style scoped>
    .home {
      text-align: left;
      font-family: 'Courier New', Courier, monospace;
      color: #555;
    }
</style>