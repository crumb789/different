<template>
  <section class="main">
    <social-btn></social-btn>
  </section>
  <section class="section-second">
    <buttons-bar></buttons-bar>
  </section>

  <section class="colors">
    <color-blur :toggle='Toggle'></color-blur>
  </section>

  <section class="toggle">
    <agr-toggle 
      @agressive-toggle='changeToggle' 
      @accept-global='submitAccept'
      :acceptFromApp='acceptFromApp'
      >
      </agr-toggle>
  </section>

  <section class="test">
    <!-- <test-soc></test-soc> -->
  </section>
</template>

<script>
import SocialBtn from './components/UI/SocialBtn.vue'
import ButtonsBar from './components/UI/ButtonsBar.vue'
import ColorBlur from './components/ColorBlur.vue'
import AgrToggle from './components/UI/AgrToggle.vue'



// import TestSoc from './components/UI/TestSoc.vue'





export default {
  name: 'App',
  components: {
    SocialBtn,
    // TestSoc,
    ButtonsBar,
    ColorBlur,
    AgrToggle,
  },
  data(){
      return{
        Toggle: true,
        acceptFromApp: false,
      }
    },
    methods:{
      changeToggle(newToggle){
        this.Toggle = newToggle
      },
      submitAccept(value){
        console.log('submit')
        console.log(value)
        this.acceptFromApp = value
      }
    },
    mounted(){
        if(sessionStorage.acceptFromApp){
            this.acceptFromApp = JSON.parse(sessionStorage.acceptFromApp)
        }
    },  
    watch:{
        acceptFromApp:{
            handler(newValue){
                sessionStorage.acceptFromApp= JSON.stringify(newValue)
            },
            deep: true
        },
    },

  }


</script>

<style lang="scss">
*{
  box-sizing: border-box;
}
html{
  box-sizing: border-box;
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
  padding-bottom: 100px;
  box-sizing: border-box;
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
.colors{
  margin-top: 80px;
  display: flex;
  justify-content: center;
}

.test{
  display: flex;
  justify-content: center
}

.toggle{
  display: flex;
  justify-content: center;
  
}

input,
textarea,
button,
select,
div,
a {
    -webkit-tap-highlight-color: transparent;
}


@media (max-width: 576px) {
  .toggle{
    margin-top: 40px;
  }

}

</style>
