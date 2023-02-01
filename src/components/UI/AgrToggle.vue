<template>
    <div class="wrapper">
        <form action="">
            <div @click="toggle = !toggle"  class="check" :class="{rotateCheck: toggle, rotateCheckBack: toggle === false }">
                <div :class="{trueToggle: toggle, falseToggle: toggle === false }" class="dot">
                </div>
                <div class="phantom" :class="{rotatePhantom: toggle, rotatePhantomBack: toggle === false }">
                </div>
            </div>
        </form>
    </div>
</template>

<script>
export default {
    data() {
        return{
            toggle: undefined
        }
    },
}
</script>

<style lang="scss" scoped>
.wrapper{

}
.check{
    position: relative;
    box-sizing: border-box;
    width: 100px;
    height: 30px;
    // background-color: rgb(14, 105, 105);
    background: rgb(255,0,0);
    background: linear-gradient(180deg, rgba(255, 0, 0, 0.308) 25%, rgba(0, 119, 255, 0.288) 100%);
    border-radius: 15px;
    padding: 2px;
    z-index: 20;
    cursor: pointer;
    
}
.dot{
    position: absolute;
    box-sizing: border-box;
    height: 26px;
    width: 26px;
    left: 2px;
    right: auto;
    background: rgb(2,0,36);
// background: linear-gradient(216deg, rgba(2,0,36,1) 0%, rgba(38,2,49,1) 21%, rgba(53,3,55,1) 72%, rgba(69,4,61,1) 87%);
    border-radius: 100%;
    border: 3px solid rebeccapurple;
    transition: 0.5s all;
    z-index: 3;
    box-shadow: 3px 0px 2px #000;

}
.phantom{
    // display: none;
    position: absolute;
    box-sizing: border-box;
    z-index: 1;
    width: 100px;
    height: 30px;
    top: 0;
    left: 0;
    background-color: #4a6464;
    // border: 2px solid;
    // opacity: 0.5;
    border-radius: 15px;
    padding: 2px;
    border: 2px solid #000000;
}

.trueToggle{
    position: absolute !important;
    // right: 2px !important;
    // left: auto !important;
    left: 72px;
    background-color: rgb(7, 160, 70);
    border: none;
    box-shadow: -3px 0px 2px #000;
    animation: rightPunch 0.3s  1  0.3s ease-out;
}

.falseToggle{
    animation: leftPunch 0.3s  1  0.3s ease-out;
}


.rotateCheckBack{
    animation: rotateBackLeft 0.2s  0.35s 1 linear ;
}
.rotateCheck{
    animation: rotateBackRight 0.2s  0.35s 1 linear ;
}


.rotatePhantomBack{
    animation: rotatePhantomLeft 0.2s  0.35s 1 linear ;
}
.rotatePhantom{
    animation: rotatePhantomRight 0.2s  0.35s 1 linear ;
    
}


////////// animation main rotate
@keyframes rotateBackLeft{
    0%{
        transform: rotateZ(3deg) translateY(2px);
        background: rgb(7, 143, 75);
        background: linear-gradient(180deg, rgba(5, 211, 211, 0.308) 25%, rgba(197, 22, 130, 0.575) 100%);
    }
    25%{
        transform: rotateZ(0deg) translateY(0px);
        background: rgb(255,0,0);
        background: linear-gradient(180deg, rgba(255, 0, 0, 0.308) 25%, rgba(0, 119, 255, 0.288) 100%);
    }
    50%{
        transform: rotateZ(-3deg) translateY(-2px);
        background: rgb(7, 143, 75);
        background: linear-gradient(180deg, rgba(5, 211, 211, 0.308) 25%, rgba(197, 22, 130, 0.575) 100%);
    }
    75%{
        transform: rotateZ(0deg) translateY(0px);
        background: rgb(255,0,0);
        background: linear-gradient(180deg, rgba(255, 0, 0, 0.308) 25%, rgba(0, 119, 255, 0.288) 100%);
    }
    100%{
        transform: rotateZ(3deg) translateY(2px);
        background: rgb(7, 143, 75);
        background: linear-gradient(180deg, rgba(5, 211, 211, 0.308) 25%, rgba(197, 22, 130, 0.575) 100%);
    }
}
@keyframes rotateBackRight{
    0%{
        transform: rotateZ(3deg) translateY(-2px);
        background: rgb(255,0,0);
        background: linear-gradient(180deg, rgba(255, 0, 0, 0.308) 25%, rgba(0, 119, 255, 0.288) 100%);
    }
    25%{
        transform: rotateZ(0deg) translateY(0px);
        background: rgb(7, 143, 75);
        background: linear-gradient(180deg, rgba(5, 211, 211, 0.308) 25%, rgba(197, 22, 130, 0.575) 100%);
    }
    50%{
        transform: rotateZ(-3deg) translateY(2px);
        background: rgb(255,0,0);
        background: linear-gradient(180deg, rgba(255, 0, 0, 0.308) 25%, rgba(0, 119, 255, 0.288) 100%);
    }
    75%{
        transform: rotateZ(0deg) translateY(0px);
        background: rgb(7, 143, 75);
        background: linear-gradient(180deg, rgba(5, 211, 211, 0.308) 25%, rgba(197, 22, 130, 0.575) 100%);
    }
    100%{
        transform: rotateZ(3deg) translateY(-2px);
        background: rgb(255,0,0);
        background: linear-gradient(180deg, rgba(255, 0, 0, 0.308) 25%, rgba(0, 119, 255, 0.288) 100%);
    }
}
//////////




////////// animation phantom rotate
@keyframes rotatePhantomLeft{
    0%{
        transform: rotateZ(-7deg) translateY(-5px);
    }
    25%{
        transform: rotateZ(0deg) translateY(0px);
    }
    50%{
        transform: rotateZ(7deg) translateY(5px);
    }
    75%{
        transform: rotateZ(0deg) translateY(0px);
    }
    100%{
        transform: rotateZ(-7deg) translateY(-5px);
    }
}
@keyframes rotatePhantomRight{
    0%{
        transform: rotateZ(-7deg) translateY(5px);
    }
    25%{
        transform: rotateZ(0deg) translateY(0px);
    }
    50%{
        transform: rotateZ(7deg) translateY(-5px);
    }
    75%{
        transform: rotateZ(0deg) translateY(0px);
    }
    100%{
        transform: rotateZ(-7deg) translateY(5px);
    }
}
//////////



////animation punch dot
@keyframes rightPunch{
    0%{
        width: 16px;
        left: 83px;
    }   
    // 50%{

    // }
    100%{
        width: 26px;
        left: 72px;
    }
}
@keyframes leftPunch{
    0%{
        width: 16px;
        left: 2px;
        border: 5px solid rebeccapurple;
    }   
    // 50%{

    // }
    100%{
        width: 26px;
        left: 2px;
    }
}
/////////




#checkbox{
    appearance: checkbox;    
}

</style>