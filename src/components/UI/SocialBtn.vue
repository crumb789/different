<template>
    <div class="wrapper">
        <a class="link" href="#">
            <div class="perspective">
                <div class="main"><i class="bi bi-slack"></i></div>
                <div class="second"></div>
                <div class="third"></div>
                <div class="four"></div>
                <div class="bottom"></div>
                <div class="left"></div>
            </div>
        </a>
        <a class="link" href="#">
            <div class="perspective">
                <div class="main"><i class="bi bi-google"></i></div>
                <div class="second"></div>
                <div class="third"></div>
                <div class="four"></div>
                <div class="bottom"></div>
                <div class="left"></div>
            </div>
        </a>
        <a class="link" href="#">
            <div class="perspective">
                <div class="main"><i class="bi bi-stack-overflow"></i></div>
                <div class="second"></div>
                <div class="third"></div>
                <div class="four"></div>
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
        box-shadow: none;
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
    z-index: 10;  
    border-radius: 3px;
    opacity: 0.6;
    i{
        font-size: 50px;
        color: #ff3860;
    }
    &:hover{
        top: -75px;
        left: 45px;
        background-color: #432875;
        opacity: 0.9;
        ~.second{
            top: -55px;
            left: 35px;
            background-color: #7c0f7c;
            opacity: 0.8;
        }
        ~.third{
            top: -35px;
            left: 25px;
            background-color: #4e1a4e;
            opacity: 0.8;
        }
        ~.four{
            top: -15px;
            left: 15px;
            background-color: #3b193b;
            box-shadow: -4px 4px 25px #000;
            opacity: 0.8;
        }
        ~.left{
            opacity: 0;
        }
        ~.bottom{
            opacity: 0;
        }
        ~.perspective{
            box-shadow: none;
        }
    }
    
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
</style>