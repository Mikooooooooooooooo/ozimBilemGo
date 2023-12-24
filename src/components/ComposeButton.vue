<template>
    <div class="composeButton">
        <div class="composeButton__header">
            <div class="composeButton__count">
                7,642
            </div>
            <Button title="+Compose Email"></Button>
        </div>
        <div class="composeButton__title">
            Total emails Subscriber
        </div>
        <div class="composeButton__description">
            Lorem, ipsum dolor sit amet consectetur adipisicing elit. Expedita excepturi libero fugiat numquam quas sapiente labore inventore iusto!
        </div>
    </div>
</template>

<script>
    import Button from './Button.vue';
    export default{
        components:{
            Button
        }
    }
</script>

<style>
    @import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500;600;700&family=Open+Sans:ital,wght@0,400;0,500;0,700;1,600&display=swap');

    .composeButton{
        padding: 30px 30px 0 ; 
        background: white ; 
        gap: 30px; 
        font-family: 'Open Sans' , sans-serif ; 
    }
    .composeButton__header{
        display: flex ;
        justify-content: space-between;
    }
    .composeButton__count{
        font-size: 40px ; 
        font-weight: 700 ; 
        color: navy;
        margin-bottom: 1.5vh ; 
    }
    .composeButton__title{
        font-size: 20px ; 
        font-weight: 700 ; 
        color: navy;
        margin-bottom: 3vh ;
    }
    .composeButton__description{
        font-size: 14px;    
        color: rgba(0, 0, 0, 0.7);
        margin-bottom: 3.5vh ; 
    }


</style>