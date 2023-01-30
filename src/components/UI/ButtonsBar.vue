<template>
    <div class="wrapper">
        <ul class="btns">
            <li v-for="li in buttonsArray" 
                :key="li.id"
                class="btn" 
                :class="{active: li.id === activeiId}"
                @click="changeButtonACtive(li.id)">

                    <i :class="li.icon " >
                    </i>
                    <div  class="btns-descr">
                        <p v-if="li.descr === 'Fold'" style="margin-left: -2px" :class="{descrActive: li.id === activeiId }">{{li.descr}}</p>
                        <p v-else :class="{descrActive: li.id === activeiId }">{{li.descr}}</p>
                    </div>

                    <div class="wrapper-buble">
                        <div class=" buble buble-left" :class="{bubleLeftActive: li.id === activeiId }"></div>
                        <div class="buble" :class="{bubleActive: li.id === activeiId }">                        
                        </div>
                        <div class="buble buble-right" :class="{bubleRightActive: li.id === activeiId }"></div>
                        <div class="buble buble-main" :class="{bubleMainActive: li.id === activeiId}"></div>

                    </div>
            </li>
        </ul>

    </div>
</template>


<script>
export default {
    data() {
        return{
            enter: false,
            activeiId: 0,
            buttonsArray: [
                {
                    "id": 0,
                    "icon": "bi bi-house-door",
                    "descr": "Home"
                },
                {
                    "id": 1,
                    "icon": "bi bi-chat-left-dots",
                    "descr": "Chat"
                },
                {
                    "id": 2,
                    "icon": "bi bi-folder",
                    "descr": "Fold"
                },
                {
                    "id": 3,
                    "icon": "bi bi-person",
                    "descr": "Profile"
                }
            ],
        }
    },
    methods:{
        changeButtonACtive(id){
            this.activeiId = id
        }
    }
}
</script>


<style lang="scss" scoped>
.wrapper{
    display: flex;
    &-buble{
        position: relative;
    }
}

.btns{
    position: relative;
    box-sizing: border-box;
    display: flex;
    height: 70px;
    // width: 500px;
    width: 90vw;
    max-width: 600px;
    margin: 0 10px;
    padding: 15px 25px 30px 25px;
    justify-content: space-between;
    background-color: #fff3ff;
    border-radius: 13px;
    overflow: hidden;
    &-descr{
        position: relative;
        p{
            position: absolute;
            margin: 0;
            margin-left: -25%;
            top: 0;
            font-size: 14px;
            font-weight: bold;
            z-index: 11;
            transition: 0.2s all;
        }
    }
}

.btn{
    list-style-type: none;
    cursor: pointer;
    transition: 0.3s all;
    i{
        color: #8294ee;
        font-size: 25px;
        transition: 0.8s all;
    }
}

.descrActive{
    top: 50px !important;
}

.buble{
    position: absolute;
    top: 50px;
    background-color: #3c4eab;
    border-radius: 100% 100% 0 0 ;
    transition: 0.3s all;
    z-index: 1;
}
.buble-left{
    width: 16px;
    height: 26px;
    left: -14.7px;
    background-color: #fff3ff;
    border-radius: 0 0 100% 0;
    z-index: 10;

}
.buble-right{
    width: 16px;
    height: 26px;
    right: -14.7px;
    background-color: #fff3ff;
    border-radius: 0 0 0 100% ;
    z-index: 10;
}
.buble-main{
    // display: none;
    width: 50px;
    height: 45px;
    left: -12px;
    border-radius: 0;
    background-color: #3c4eab;
}
.bubleMainActive{
    display: block;
    width: 50px;
    height: 50px;
    top: 9px;
    background-color: #3c4eab;

}

.bubleActive{
    width: 25px;
    height: 25px;
    top: 0;
}
.bubleLeftActive{
    top: 1px;
}
.bubleRightActive{
    top: 1px;
}




.active{
    transition: 0.3s all;
    i{
        color: #3c4eab;
    }
}







////media adaptation
@media (max-width: 576px) {


}
</style>