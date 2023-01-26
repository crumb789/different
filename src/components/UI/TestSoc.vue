<template>
    <div class="wrapper">
        {{enter}}
        <a class="link" href="#">
            <div @mouseenter="enter = true, id = 1" @mouseleave="enter = false, id = 0" class="perspective">
                <div  class="main" :class="{MainHover: enter === true && id === 1}" >
                    <i class="bi bi-slack">
                    </i>
                </div>
                <div class="second" :class="{SecondHover: enter === true && id === 1}"></div>
                <div class="third" :class="{ThirdHover: enter === true && id === 1}"></div>
                <div class="four" :class="{FourHover: enter === true && id === 1}"></div>
                <div class="place"></div>
                <div class="bottom"></div>
                <div class="left"></div>
            </div>
        </a>


        <a class="link" href="#">
            <div @mouseenter="enter = true, id = 2" @mouseleave="enter = false, id = 0" class="perspective">
                <div  class="main" :class="{MainHover: enter === true && id === 2}" >
                    <i class="bi bi-google"></i>
                </div>
                <div class="second" :class="{SecondHover: enter === true && id === 2}"></div>
                <div class="third" :class="{ThirdHover: enter === true && id === 2}"></div>
                <div class="four" :class="{FourHover: enter === true && id === 2}"></div>
                <div class="place"></div>
                <div class="bottom"></div>
                <div class="left"></div>
            </div>
        </a>


        <a class="link" href="#">
            <div @mouseenter="enter = true, id = 3" @mouseleave="enter = false, id = 0" class="perspective">
                <div  class="main" :class="{MainHover: enter === true && id === 3}" >
                    <i class="bi bi-stack-overflow"></i>
                </div>
                <div class="second" :class="{SecondHover: enter === true && id === 3}"></div>
                <div class="third" :class="{ThirdHover: enter === true && id === 3}"></div>
                <div class="four" :class="{FourHover: enter === true && id === 3}"></div>
                <div class="place"></div>
                <div class="bottom"></div>
                <div class="left"></div>
            </div>
        </a>

    </div>
</template>


<script>
export default {
    data() {
        return{
            enter: false,
            id: 0
        }
    },
}
</script>


<style lang="scss" scoped>
.wrapper{
    display: flex;
}
.link{
    &:nth-child(1){
        z-index: 3;
    }
    &:nth-child(2){
        z-index: 2;
    }
    &:nth-child(3){
        z-index: 1;
    }
}
.perspective {
    position: relative;
    width: 100px;
    height: 200px;
    margin: 0 10px;
    transform-style: preserve-3d;
    transition: all 500ms ease-in;
    transform: rotateY(20deg) rotateX(60deg) rotateZ(-10deg);
    transform: rotateY(15deg) rotateX(50deg) rotateZ(-15deg);
    box-shadow: -40px 80px 80px -10px rgba(0, 0, 0, 0.7);
    cursor: pointer;
    display: inline-block;
    transition: 0.2s all;
    &:hover{
        // box-shadow: none;
    }

}

.main {
    position: absolute;
    top: 0px;
    left: 0px;
    width: 100px;
    height: 200px;
    transform: translateZ(16px);
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: #363436;
    transition: 0.5s all;
    z-index: 1000;  
    border-radius: 3px;
    opacity: 0.6;
    i{
        font-size: 50px;
        color: #ff3860;
    }
    
}
.MainHover{
    top: -75px ; 
    left: 40px;
    background-color: #432875;
    border-radius: 8px;
    // background: rgb(238,174,202);
    // background: radial-gradient(circle, rgb(207 44 150) 0%, rgb(126 37 126) 100%);
    animation: gradient 4s infinite linear;
    opacity: 0.85;
}

.SecondHover{
    top: -55px !important;
    left: 30px !important;
    border-radius: 6px !important;
    background-color: #7c0f7c !important;
    opacity: 0.7 !important;
}
.ThirdHover{
    top: -35px !important;
    left: 20px !important;
    border-radius: 4px !important;
    background-color: #4e1a4e !important;
    opacity: 0.65 !important;
}

.FourHover{
    top: -15px !important;
    left: 10px !important;
    border-radius: 3px !important;
    background-color: #3b193b !important;
    box-shadow: -4px 4px 25px #000 !important;
    opacity: 0.6 !important; 
}
 

.second {
    position: absolute;
    top: 0px;
    left: 0px;
    width: 100px;
    height: 200px;
    transform: translateZ(16px);
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: #363436;
    transition: 0.5s all;  
    z-index: 3;  
}
.third {
    position: absolute;
    top: 0px;
    left: 0px;
    width: 100px;
    height: 200px;
    transform: translateZ(16px);
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: #363436;
    transition: 0.5s all;  
    z-index: 2;  
}
.four {
    position: absolute;
    top: 0px;
    left: 0px;
    width: 100px;
    height: 200px;
    transform: translateZ(16px);
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: #363436;
    transition: 0.5s all;  
    z-index: 1;  
    
}
.place{
    position: absolute;
    top: 0px;
    left: 0px;
    width: 100px;
    height: 200px;
    transform: translateZ(16px);
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: rgb(44 35 44 / 98%);
    transition: 0.5s all;  
    z-index: 0;  
}



.bottom,
.left {
    position: absolute;
    width: 100px;
    height: 200px;
    display: block;
    transition: all 1s linear;
    overflow: hidden;
    transform: translateZ(16px);
    transition: 0.5s all;
}

.left {
    transform: rotateY(270deg) translateX(-1px);
    transform-origin: center left;
    width: 18px;
    background-color: #222022;
}

.bottom {
    transform: rotateX(90deg) translateY(15px) translateZ(-180px);
    transform-origin: bottom center;
    height: 18px;
    background-color: #222022;
}

.bottom img {
    transform: rotateX(180deg);
    width: 100%;
    height: 200px;
    left: 0px;
}




////keyframes
@keyframes gradient{
    0%{
        background-color: #5b4681;
        background: radial-gradient(235deg, #7647cc, 0%, #5a34a0, 100%);
        transform: rotate(0deg) translateZ(16px);
        opacity: 0.75;
    }
    25%{
        background-color: #5b4681;
        background: radial-gradient(235deg, #7647cc, 0%, #5a34a0, 100%);
        transform: rotate(2deg) translateZ(16px);
        opacity: 0.8;
    }
    50%{
        background-color: #4b2592;
        background: radial-gradient(235deg, #7547ca, 0%, #3f1d7e, 100%);
        transform: rotate(0deg) translateZ(16px);
        opacity: 0.75;
    }
    75%{
        background-color: #6946aa;
        background: radial-gradient(235deg, #4e2d8b, 0%, #531fb4, 100%);
        transform: rotate(-2deg) translateZ(16px);
        opacity: 0.8;
    }
    100%{
        background-color: #5b4681;
        background: radial-gradient(235deg, #7647cc, 0%, #5a34a0, 100%);
        transform: rotate(0deg) translateZ(16px);
        opacity: 0.75;
    }
}







////media adaptation
@media (max-width: 576px) {
  .wrapper{
    row-gap: 10px;
  }
  .perspective{
    width: 50px;
    height: 100px;
  }
  .main{
    width: 50px;
    height: 100px;
    i{
        font-size: 25px;
    }
  }

    .second{
        width: 50px;
        height: 100px;
    }
    .third {
        width: 50px;
        height: 100px;
    }
    .four {
        width: 50px;
        height: 100px;
    }
    .place{
        width: 50px;
        height: 100px;
    }

    .bottom,
    .left {
        position: absolute;
        width: 50px;
        height: 100px;
    }
    .bottom{
        transform: rotateX(90deg) translateY(15px) translateZ(-86px);
        width: 50px;
        height: 12px;
    }
    .left{
        transform: rotateY(270deg) translateX(4px); 
        width: 12px;
    }
}
</style>