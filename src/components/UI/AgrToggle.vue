<template>
    <div class="wrapper">
        <form action="">
            <div @click="toggle = !toggle"  class="check" :class="{rotateCheck: toggle, rotateCheckBack: toggle === false }">
                <div :class="{trueToggle: toggle, falseToggle: toggle === false }" class="dot">

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
    background-color: azure;
    border-radius: 15px;
    padding: 2px;
    cursor: pointer;
    
}
.dot{
    position: absolute;
    box-sizing: border-box;
    height: 26px;
    width: 26px;
    left: 2px;
    right: auto;
    background-color: azure;
    border-radius: 100%;
    border: 3px solid rebeccapurple;
    transition: 0.5s all;
}

.trueToggle{
    position: absolute !important;
    // right: 2px !important;
    // left: auto !important;
    left: 72px;
    background-color: rgb(7, 160, 70);
    border: none;
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
@keyframes rotateBackLeft{
    0%{
        transform: rotateZ(5deg);
    }
    25%{
        transform: rotateZ(0deg);
    }
    50%{
        transform: rotateZ(-5deg);
    }
    75%{
        transform: rotateZ(0deg);
    }
    100%{
        transform: rotateZ(5deg);
    }
}
@keyframes rotateBackRight{
    0%{
        transform: rotateZ(5deg);
    }
    25%{
        transform: rotateZ(0deg);
    }
    50%{
        transform: rotateZ(-5deg);
    }
    75%{
        transform: rotateZ(0deg);
    }
    100%{
        transform: rotateZ(5deg);
    }
}

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


#checkbox{
    appearance: checkbox;    
}

</style>