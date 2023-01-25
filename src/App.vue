<template>
  <section class="main">
    <social-btn></social-btn>
  </section>
</template>

<script>
import SocialBtn from './components/UI/SocialBtn.vue'


export default {
  name: 'App',
  components: {
    SocialBtn,
  }
}
</script>

<style lang="scss">
html{
  background-color: #2c3e50;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  
}

.main{
  display: flex;
  justify-content: center
}


</style>
