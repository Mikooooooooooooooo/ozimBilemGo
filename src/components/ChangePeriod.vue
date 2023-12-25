<template> 
    <div class="change__period">
        <div class="change__period-top"  @click="show = !show">
            <img src="../assets/calendar.svg" alt="" class="change__period-icon">
            <div class="change__period-text">
                <div class="change__period-title">
                    Change Periode
                </div>
                <div class="change__period-description">
                    {{date}}
                </div>
            </div>
            <img src="../assets/down.png" alt="" class="change__period-button">
        </div>
        <div v-if="show" class="change__period-bottom">
            <div class="slidecontainer">
                <input v-on:input="changeDate($event)" type="range" min="1" max="10" :value="val" class="slider" id="myRange">
            </div>
        </div>
    </div>
</template>

<script>
    export default{
        data() {
            return {
                show: false , 
                val: 5 , 
                date: 'August - October, 2020' , 
                arr: ['November - January, 2019' , 'January - March, 2020', 'March - May, 2020','May - August, 2020' , 'August - November, 2020','November - January, 2020','January - March, 2021','March - May, 2021' , 'May - August, 2021' , 'August-November , 2021' , 'November-January , 2021']
            }
        } , 
        methods: {
            changeDate(event){
                this.date = this.arr[event.target.value]
                this.val = event.target.value
            }
        }
    }
</script>

<style>
    .change__period{
        width: 330px ; 
        padding: 10px 20px; 
        background: white ; 
    }
    .change__period-top{
        display: flex ; 
        position: relative ; 
        cursor: pointer ;
    }
    .change__period-icon{
        height: 25px ; 
        width: 25px; 
        margin: 7px 7px 0 0  ;
    }
    .change__period-title{
      font-size: 17px;
      font-weight: 600;
      font-family: Verdana, Geneva, Tahoma, sans-serif;
      color: navy;
      padding-bottom: .5vh ; 
    }
    .change__period-text{
        padding: 0 30px 0 10px ; 
    }
    .change__period-description{ 
        color: rgba(0, 0, 0, 0.7);
        font-size: 12px ; 
    }
    .change__period-button{
        position: absolute ; 
        right: 5px ;
        width: 20px ; 
        height: 20px ; 
        margin-top: 10px; 
    }
    .change__period-bottom{
        width: 100% ; 
        height: 30px ; 
    }

    .slidecontainer {
        margin: 2vh 0 0 ;
        width: 100%; 
    }

    .slider {
        appearance: none;
        width: 100%; 
        height: 15px;
        background: #d3d3d3; 
        outline: none; 
        opacity: 0.7; 
        transition: opacity .2s;
    }

    .slider:hover {
        opacity: 1; 
    }
</style>

