<template> 
    <div class="dropdawn">
        <div class="dropdawn__top" v-on:click="show = !show">
            <div class="dropdawn__title">
                {{ title }}
            </div>
            <img src="../assets/down.png"  alt=""  class="dropdawn__button">
        </div>
        <div v-if="show" v-for="(button , index) in buttons" v-on:click="swap(index)" class="dropdawn__bottom">
            {{ button }}
        </div>
    </div>
</template> 

<script>
    export default{
        props: ['titlee' , 'buttons' ,  'buttonss'] , 
        data() {
            return {
                show: false , 
                title: this.titlee  , 
            }
        } , 
        methods:{
            swap(index) {
                const temp = this.title ; 
                this.title = this.buttons[index] ; 
                this.buttons[index] = temp ; 
                if (this.title == "This Month"){
                    this.emitValue(1)
                }
                if (this.title == "Prev Month"){
                    this.emitValue(2)
                }
                if (this.title == "Next Month"){
                    this.emitValue(3)
                }
            } , 
            emitValue(type) {
                console.log(type)
                this.$emit('click', type )
            }
        }
    }
</script>

<style>
    @import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500;600;700&family=Open+Sans:ital,wght@0,400;0,500;0,700;1,600&display=swap');
    
    .dropdawn{
        border: 1px solid  rgba(0, 0, 0, 0.7);
    }
    
    .dropdawn__top{
        display: flex ; 
        padding: 10px 15px; 
        width: 140px ; 
        justify-content: space-between ;
        cursor: pointer;
    }
    .dropdawn__title{
        font-size: 14px;
        font-weight: 500;
        font-family: 'Open Sans' , sans-serif;
        color: navy;
    }
    .dropdawn__button{
        width: 20px ; 
        height: 20px ; 
    }
    .dropdawn__bottom{
        padding: 10px 15px; 
        width: 140px ; 
        font-size: 14px;
        font-weight: 500;
        font-family: 'Open Sans' , sans-serif;
        color: navy;    
        cursor: pointer ; 
    }
    .dropdawn__bottom:hover{
        background: #ededed; 
    }
</style>