<template>
    <div class="button" :style="{ padding: `${parseInt(padding / 2.66)}px ${padding}px` }" >
        {{ title }}
    </div>
</template>

<script>
    export default{
        props: ['title' , 'padding']
    }
</script>

<style>
    .button{
        width: fit-content; 
        height: fit-content;
        padding: 15px 40px; 
        background: #ef6d4d;
        color: white; 
        font-weight: 500;
        font-size: 16px; 
        cursor: pointer ; 
        transition: background-color 0.3s ease;
    }
    .button:hover{
        background-color: #d95c3d;
        box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
    }

</style>