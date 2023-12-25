<template> 
    <div class="tag">
        {{ title }}
    </div>
</template>

<script>
    export default{
        props: ['title']
    }
</script>

<style>
    @import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500;600;700&family=Open+Sans:ital,wght@0,400;0,500;0,700;1,600&display=swap');
    .tag{
        padding: 15px; 
        color: #ef6d4d;
        font-weight: 600 ;
        font-size: 15px; 
        background: rgba(255, 127, 80, 0.3) ;
    }
</style>