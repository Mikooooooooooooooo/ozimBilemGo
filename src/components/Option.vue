<template> 
    <div class="option">
        <div class="option__l">
            <div class="option__icon" :style="{background: color}">

            </div>
            <div class="option__title">
                {{ title }}
            </div>
        </div>
        <div class="option__count">
            {{ count }}
        </div>
    </div>
</template>

<script>
    export default {
        props:['color' , 'title' , 'count']
    }
</script>

<style>
    @import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500;600;700&family=Open+Sans:ital,wght@0,400;0,500;0,700;1,600&display=swap');
    .option{
        display: flex; 
        justify-content: space-between ; 
        font-family: 'Open Sans' , sans-serif ; 
        color: navy;
        margin: 2vh 0 ; 
    }
    .option__l{
        display: flex; 
        gap: 20px; 
    }
    .option__icon{
        width: 20px; 
        height: 20px; 
    }
    .option__title{
        font-size: 14px; 
        font-weight: 500; 
    }
    .option__count{
        font-size: 20px; 
        font-weight: 600;
    }

</style>