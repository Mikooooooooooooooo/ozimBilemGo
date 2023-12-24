<template>
    <div class="menu-item" id="menu-item" :style="{ backgroundColor: background, color: textColor }"
    @mouseover="isMouseOver = true"
    @mouseleave="isMouseOver = false">
        <img :src="imageSrc" alt="">
        <p>{{itemName}}</p>
    </div>
</template>

<script scoped>
    export default{
        props:{
            imageName: {
                type: String,
                required: true
            },
            itemName: {
                type: String,
                required: true
            }
        },
        data() {
            return {
                isMouseOver: false , 
                imageSrc: require("../assets/" + this.imageName)
            };
        },
        computed: {
            background() {
                return this.isMouseOver ? 'rgba(255, 127, 80, 0.3)' : '';
            },
            textColor() {
                return this.isMouseOver ? 'rgb(255, 106, 69)' : 'rgba(0, 0, 0, 0.7)';
            }
        }
    }
</script>

<style scoped>
    .menu-item {
        display: flex;
        padding: 10px;
        width: 180px;
        height: 50px;
        align-items: center;
        font-size: 14px;
        color: rgba(0, 0, 0, 0.7);
        cursor: pointer;
        z-index: 1;
    }
    .menu-item p{
        z-index: 2;
    }
    .menu-item img{
        width: 20px;
        height: 20px;
        margin-right: 15px;
    }
</style>