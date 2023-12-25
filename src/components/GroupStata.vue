<template> 
    <div class="group__stata">
        <Stata v-for="stat in stats" :item="stat" />
    </div>
</template>

<script>
    import Stata from './Stata.vue'
    export default{
        data() { 
            return { 
                stats: [
                    {count: '932' , title: 'Project' , source: 'icon1.svg'} , 
                    {count: '1,032' , title: 'Inquires' , source: 'icon2.svg'} , 
                    {count: '102k' , title: 'Invesment' , source: 'icon3.svg'} , 
                    {count: '32k' , title: 'Assets' , source: 'icon4.svg'} , 
                ]
            }
        } , 
        components: {
            Stata , 
        }
    }
</script>

<style>
    .group__stata{
        display: flex ; 
        gap: 15px ; 
        width: 100% ; 
        margin: 3vh auto ; 
    }
</style>