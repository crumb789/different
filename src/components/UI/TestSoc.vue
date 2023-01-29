<template>
    <div class="wrapper">
        <ul class="bnts">
            <li class="btn"><i class="bi bi-house-door"></i></li>
            <li class="btn"><i class="bi bi-chat-left-dots"></i></li>
            <li class="btn"><i class="bi bi-folder"></i></li>
            <li class="btn"><i class="bi bi-person"></i></li>
        </ul>

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

.btns{
    display: flex;
}

.btn{
    list-style-type: none;
    i{
        color: #fff;
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