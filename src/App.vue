<template>
  <section class="main">
    <social-btn></social-btn>
  </section>
  <section class="test">
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
  background-color: #312d36;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='4' height='4' viewBox='0 0 4 4'%3E%3Cpath fill='%235d00f3' fill-opacity='0.4' d='M1 3h1v1H1V3zm2-2h1v1H3V1z'%3E%3C/path%3E%3C/svg%3E");
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
.test{
  display: flex;
  justify-content: center
}


</style>
