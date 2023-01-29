<template>
  <section class="main">
    <social-btn></social-btn>
  </section>
  <section class="section-second">
    <buttons-bar></buttons-bar>
  </section>


  <section class="test">
    <!-- <test-soc></test-soc> -->
  </section>
</template>

<script>
import SocialBtn from './components/UI/SocialBtn.vue'
import ButtonsBar from './components/UI/ButtonsBar.vue'


// import TestSoc from './components/UI/TestSoc.vue'





export default {
  name: 'App',
  components: {
    SocialBtn,
    // TestSoc,
    ButtonsBar,
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
  &:focus{
    outline: none;
  }
}

.main{
  display: flex;
  justify-content: center
}
.section-second{
  margin-top: 80px;
  display: flex;
  justify-content: center
}
.test{
  display: flex;
  justify-content: center
}

input,
textarea,
button,
select,
div,
a {
    -webkit-tap-highlight-color: transparent;
}


</style>
