<template>
    <div class="stata">
        <img :src="imageSrc" class="stata__icon" alt="">
        <div class="stata__text">
            <div class="stata__text-count">
                {{ item.count }}
            </div>
            <div class="stata__text-title">
                {{ item.title }}
            </div>
        </div>
    </div>
</template>

<script>
    export default{ 
        props: ['item'] , 
        data() {
            return {
                imageSrc: require("../assets/" + this.item.source)
            }
        }
    }
</script>

<style>

    .stata{
        display: flex ; 
        padding: 25px ; 
        width: 25% ; 
        font-family: Verdana, Geneva, Tahoma, sans-serif;
        background: white ; 
    }

    .stata__icon{
        width: 50px ; 
        height: 50px ; 
        padding: 10px ; 
        border: 1px solid gray ; 
    }

    .stata__text{
        margin-left: 20px ;
    }

    .stata__text-count{
        font-size: 24px ; 
        font-weight: 600 ; 
        color: navy;
        padding-bottom: 1vh;
    }

    .stata__text-title{
        color: rgba(0, 0, 0, 0.7); 
        font-size: 14px ;
    }
</style>