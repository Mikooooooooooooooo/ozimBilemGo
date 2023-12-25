<template> 
    <div class="status">
        <div class="status__header">
            <div class="status__title">
                Server Status
            </div>
            <img src="../assets/other.svg" alt="" class="status__other">
        </div>
        <div class="status__items">
            <StatusItem v-for="status in status_list" :color="status.color" :height="status.height" :title="status.title" />
        </div>
        <div class="status__options">
            <div class="status__option">
                <div class="status__option-title">
                    Country
                </div>
                <div class="status__option-description">
                    Indonesia
                </div>
            </div>
            <div class="status__option">
                <div class="status__option-title">
                    Domain
                </div>
                <div class="status__option-description">
                    website.com
                </div>
            </div>
            <div class="status__option">
                <img src="../assets/up.svg" alt="" class="status__option-icon">
                <div class="status__option-description">
                    2.0 mbps
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import StatusItem from './StatusItem.vue';
    export default{
        components:{
             StatusItem
        } , 
        data() {
            return { 
                status_list: [ 
                    {title: '10 AM' , color: '#DC143C' , height: '70'} , 
                    {title: '8 AM' , color: '#228B22' , height: '95'} , 
                    {title: '6 AM' , color: '#228B22' , height: '80'} , 
                    {title: '4 AM' , color: '#FFEB3B' , height: '80'} , 
                    {title: '2 AM' , color: '#DC143C' , height: '40'} , 

                ]
            }
        }
    }
</script>
   
<style>

    @import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500;600;700&family=Open+Sans:ital,wght@0,400;0,500;0,700;1,600&display=swap');

    .status{ 
        margin-top: 4vh ; 
        width: 100% ;
        padding: 30px; 
        font-family: 'Open Sans' , sans-serif ; 
        background: white; 
    } 
    .status__title{
        font-size: 26px ; 
        font-weight: 700 ; 
        color: navy;
    }
    .status__header{
        display: flex; 
        justify-content: space-between;
    }
    .status__other{
        margin-top: 10px ; 
    }
    .status__items{
        margin: 2vh 0 3vh ; 
    }
    .status__options{
        display: flex; 
        justify-content: space-between;
    }
    .status__option-title{
        color: rgba(0, 0, 0, 0.7);
        font-size: 14px; 
    }
    .status__option-title:not(:last-of-type){
        padding-bottom: .5vh ; 
    }
    .status__option-description{
        font-size: 14px ; 
        font-weight: 700 ; 
        color: navy;
    }
</style>