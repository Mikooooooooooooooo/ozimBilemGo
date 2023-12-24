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
                    {count: '932' , title: 'Project' , source: 'Item 1.png'} , 
                    {count: '1,032' , title: 'Inquires' , source: 'Item 1.png'} , 
                    {count: '102k' , title: 'Invesment' , source: 'Item 1.png'} , 
                    {count: '32k' , title: 'Assets' , source: 'Item 1.png'} , 
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