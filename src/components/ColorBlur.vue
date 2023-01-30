<template>
    <div class="wrapper">

        <div class="wrapper-result">
            <ul :class="{blurActive: blurBox === true}">
                <li :style="{backgroundColor: topLeft}"></li>
                <li :style="{backgroundColor: topRight}"></li>
                <li :style="{backgroundColor: bottomLeft}"></li>
                <li :style="{backgroundColor: bottomRight}"></li>
            </ul>
        </div>


        <form action="#" class="wrapper-colors">
            <div class="box">
                <label for="topLeft"> Top Left</label>
                <input type="color" v-model="topLeft">
            </div>
            
            <div class="box">
                <label for="topRight"> Top Right</label>
                <input type="color" v-model="topRight">
            </div>

            <div class="box">
                <label for="bottomLeft"> Bottom Left</label>    
                <input type="color" v-model="bottomLeft">
            </div>

            <div class="box">
                <label for="bottomRight"> Bottom Right</label>
                <input type="color" v-model="bottomRight">
            </div>

            <div class="box">
                <label for="blurBox"> Blur </label>
                <input type="checkbox" v-model="blurBox">
            </div>

        </form>
    </div>
</template>

<script>
export default {
    data() {
        return{
            topLeft: '#fff3ff',
            topRight: '#1cb72c',
            bottomLeft: '#911b1b',
            bottomRight: '#a2b71c',
            blurBox: true,
        }
    },
}
</script>

<style lang="scss" scoped>
.wrapper{
    display: flex;
    flex-direction: column;
    align-items: center;
    row-gap: 40px;
}
.wrapper-colors{
    display: grid;
    max-width: 720px;
    grid-template-rows: 1fr 1fr;
    grid-template-columns: 1fr 1fr;
    gap: 15px;
}

.wrapper-result{
    width: 300px;
    height: 300px;
    border-radius: 3px;
    ul{
        position: relative;
        width: 100%;
        height: 100%;
        display: grid;
        grid-template-rows: 50% 50%;
        grid-template-columns: 50% 50%;
        padding: 0;
        li{
            height: 100%;
            width: 100%;
            list-style-type: none;
        }

    }
}

.blurActive{
    &::after{
            content: '';
            position: absolute;
            width: 100%;
            height: 100%;
            backdrop-filter: blur(var(--blur, 10vmin));
        }
}


.box{
    width: 200px;
    height: 100px;
    display: flex;
    justify-content: space-around;
    align-items: center;
    border: 2px dotted #fff3ff;
    color: #fff3ff;
}

@media (max-width: 576px) {
    .wrapper-colors{
        display: grid;
        max-width: 720px;
        grid-template-rows: 104px 104px ;
        grid-template-columns: 140px 140px;
        gap: 5px;
    }
    .box{
        width: 98%;
        flex-direction: column;
    }

}
</style>