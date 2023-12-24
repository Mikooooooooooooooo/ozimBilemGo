<template>
    <div class="graphchart">
        <div class="graphchart__header">
            <div class="graphchart__title">
                Statistic
            </div>
            <div class="graphchart__title-r">
                <Dropdawn @click="handleChildValueChange" titlee="This Month"  :buttons="graphchart_buttons" :buttonss="graphchart_buttonss" />
                <img src="../assets/other.svg" class="graphchart__header-other" alt="">
            </div>
        </div>
        
        <div class="graphchart__graph">
            <div class="graphchart__numbers">
                <div class="graphchart__number">
                    125
                </div>
                <div class="graphchart__number">
                    100
                </div>
                <div class="graphchart__number">
                    75
                </div>
                <div class="graphchart__number">
                    50
                </div>
                <div class="graphchart__number">
                    25
                </div>
                <div class="graphchart__number">
                    0
                </div>
            </div>
            <div class="graph">
                    <GraphItem class="elem" v-for="(element, index) in styles" 
                        :key="index" 
                        :title="element.elementName" 
                        :color1="element.color1"
                        :color2="element.color2"
                        :height1="element.height1"
                        :height2="element.height2"
                        >
                    </GraphItem>
            </div>
            <div class="graphchart__stats">
                <div class="graphchart__stats-tags">
                    <div class="graphchart__stats-tag">
                        <div class="graphchart__stats-tag-icon">
                            <svg xmlns="http://www.w3.org/2000/svg" height="12"  width="12" fill="#ef6d4d" viewBox="0 0 512 512"><path  d="M464 256A208 208 0 1 0 48 256a208 208 0 1 0 416 0zM0 256a256 256 0 1 1 512 0A256 256 0 1 1 0 256z"/></svg>
                        </div>
                        <div class="graphchart__stats-tag-title">
                            Income
                        </div>
                    </div>
                    <div class="graphchart__stats-tag">
                        <div class="graphchart__stats-tag-icon">
                            <svg xmlns="http://www.w3.org/2000/svg" height="12"  width="12" fill="#ebbe5e" viewBox="0 0 512 512"><path  d="M464 256A208 208 0 1 0 48 256a208 208 0 1 0 416 0zM0 256a256 256 0 1 1 512 0A256 256 0 1 1 0 256z"/></svg>
                        </div>
                        <div class="graphchart__stats-tag-title">
                            Expense
                        </div>
                    </div>
                </div>
                <div class="graphchart__stats-options">
                    <div class="graphchart__stats-option">
                        <div class="graphchart__stats-option-title">
                            Income
                        </div>
                        <div class="graphchart__stats-option-count">
                            {{amount}}
                        </div>
                        <div class="graphchart__stats-option-bottom">
                            <svg class="graphchart__stats-option-icon" fill="#02ba70" xmlns="http://www.w3.org/2000/svg" height="20" width="20" viewBox="0 0 512 512"><path d="M256 512A256 256 0 1 0 256 0a256 256 0 1 0 0 512zM135.1 217.4l107.1-99.9c3.8-3.5 8.7-5.5 13.8-5.5s10.1 2 13.8 5.5l107.1 99.9c4.5 4.2 7.1 10.1 7.1 16.3c0 12.3-10 22.3-22.3 22.3H304v96c0 17.7-14.3 32-32 32H240c-17.7 0-32-14.3-32-32V256H150.3C138 256 128 246 128 233.7c0-6.2 2.6-12.1 7.1-16.3z"/></svg>
                            <div class="graphchart__stats-option-percent">
                                {{ percent }}
                            </div>
                        </div>
                    </div>
                    <div class="graphchart__stats-option">
                        <div class="graphchart__stats-option-title">
                            Expense
                        </div>
                        <div class="graphchart__stats-option-count">
                            {{amount}}
                        </div>
                        <div class="graphchart__stats-option-bottom">
                            <svg class="graphchart__stats-option-icon" fill="#ba3902" xmlns="http://www.w3.org/2000/svg" height="20" width="20" viewBox="0 0 512 512"><path d="M256 0a256 256 0 1 0 0 512A256 256 0 1 0 256 0zM376.9 294.6L269.8 394.5c-3.8 3.5-8.7 5.5-13.8 5.5s-10.1-2-13.8-5.5L135.1 294.6c-4.5-4.2-7.1-10.1-7.1-16.3c0-12.3 10-22.3 22.3-22.3l57.7 0 0-96c0-17.7 14.3-32 32-32l32 0c17.7 0 32 14.3 32 32l0 96 57.7 0c12.3 0 22.3 10 22.3 22.3c0 6.2-2.6 12.1-7.1 16.3z"/></svg>
                            <div class="graphchart__stats-option-percentt">
                                {{ percent }}
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

</template>

<script>
    import GraphItem from './GraphItem.vue';
    import Dropdawn from './Dropdawn.vue';

    export default {
        components: {
            GraphItem , 
            Dropdawn
        },
       
        data() {
            return {
                amount: '$12,890,00' , 
                percent: '15%' ,
                amounts:['$12,890,00' , '$11,625,00' , '$14,721,00'] , 
                percents: ['15%' , '7%' , '27%'] , 
                styles: [
                    {elementName: 'Jan', color1: '#ef6d4d', height1: '65%' , color2:'rgba(241,199,103,255)' , height2: '80%'},
                    {elementName: 'Feb', color1: '#ef6d4d', height1: '50%' , color2:'rgba(241,199,103,255)' , height2: '45%'},
                    {elementName: 'Mar', color1: '#ef6d4d', height1: '40%' , color2:'rgba(241,199,103,255)' , height2: '45%'},
                    {elementName: 'Apr', color1: '#ef6d4d', height1: '47%' , color2:'rgba(241,199,103,255)' , height2: '49%'},
                    {elementName: 'May', color1: '#ef6d4d', height1: '55%' , color2:'rgba(241,199,103,255)' , height2: '60%'},
                    {elementName: 'Jun', color1: '#ef6d4d', height1: '70%' , color2:'rgba(241,199,103,255)' , height2: '60%'},
                    {elementName: 'Jul', color1: '#ef6d4d', height1: '85%' , color2:'rgba(241,199,103,255)' , height2: '80%'},
                    {elementName: 'Aug', color1: '#ef6d4d', height1: '40%' , color2:'rgba(241,199,103,255)' , height2: '43%'},
                    {elementName: 'Sep', color1: '#ef6d4d', height1: '42%' , color2:'rgba(241,199,103,255)' , height2: '37%'},
                    {elementName: 'Oct', color1: '#ef6d4d', height1: '25%' , color2:'rgba(241,199,103,255)' , height2: '27%'},
                    {elementName: 'Nov', color1: '#ef6d4d', height1: '70%' , color2:'rgba(241,199,103,255)' , height2: '72%'},
                    {elementName: 'Dec', color1: '#ef6d4d', height1: '61%' , color2:'rgba(241,199,103,255)' , height2: '70%'},
                ] , 
                styles_list:[
                    [
                        {elementName: 'Jan', color1: '#ef6d4d', height1: '65%' , color2:'rgba(241,199,103,255)' , height2: '80%'},
                        {elementName: 'Feb', color1: '#ef6d4d', height1: '50%' , color2:'rgba(241,199,103,255)' , height2: '45%'},
                        {elementName: 'Mar', color1: '#ef6d4d', height1: '40%' , color2:'rgba(241,199,103,255)' , height2: '45%'},
                        {elementName: 'Apr', color1: '#ef6d4d', height1: '47%' , color2:'rgba(241,199,103,255)' , height2: '49%'},
                        {elementName: 'May', color1: '#ef6d4d', height1: '55%' , color2:'rgba(241,199,103,255)' , height2: '60%'},
                        {elementName: 'Jun', color1: '#ef6d4d', height1: '70%' , color2:'rgba(241,199,103,255)' , height2: '60%'},
                        {elementName: 'Jul', color1: '#ef6d4d', height1: '85%' , color2:'rgba(241,199,103,255)' , height2: '80%'},
                        {elementName: 'Aug', color1: '#ef6d4d', height1: '40%' , color2:'rgba(241,199,103,255)' , height2: '43%'},
                        {elementName: 'Sep', color1: '#ef6d4d', height1: '42%' , color2:'rgba(241,199,103,255)' , height2: '37%'},
                        {elementName: 'Oct', color1: '#ef6d4d', height1: '25%' , color2:'rgba(241,199,103,255)' , height2: '27%'},
                        {elementName: 'Nov', color1: '#ef6d4d', height1: '70%' , color2:'rgba(241,199,103,255)' , height2: '72%'},
                        {elementName: 'Dec', color1: '#ef6d4d', height1: '61%' , color2:'rgba(241,199,103,255)' , height2: '70%'},
                    ],
                    [
                        {elementName: 'Jan', color1: '#ef6d4d', height1: '15%' , color2:'rgba(241,199,103,255)' , height2: '25%'},
                        {elementName: 'Feb', color1: '#ef6d4d', height1: '30%' , color2:'rgba(241,199,103,255)' , height2: '45%'},
                        {elementName: 'Mar', color1: '#ef6d4d', height1: '5%' , color2:'rgba(241,199,103,255)' , height2: '20%'},
                        {elementName: 'Apr', color1: '#ef6d4d', height1: '45%' , color2:'rgba(241,199,103,255)' , height2: '15%'},
                        {elementName: 'May', color1: '#ef6d4d', height1: '40%' , color2:'rgba(241,199,103,255)' , height2: '50%'},
                        {elementName: 'Jun', color1: '#ef6d4d', height1: '60%' , color2:'rgba(241,199,103,255)' , height2: '55%'},
                        {elementName: 'Jul', color1: '#ef6d4d', height1: '75%' , color2:'rgba(241,199,103,255)' , height2: '75%'},
                        {elementName: 'Aug', color1: '#ef6d4d', height1: '35%' , color2:'rgba(241,199,103,255)' , height2: '40%'},
                        {elementName: 'Sep', color1: '#ef6d4d', height1: '37%' , color2:'rgba(241,199,103,255)' , height2: '32%'},
                        {elementName: 'Oct', color1: '#ef6d4d', height1: '20%' , color2:'rgba(241,199,103,255)' , height2: '22%'},
                        {elementName: 'Nov', color1: '#ef6d4d', height1: '65%' , color2:'rgba(241,199,103,255)' , height2: '68%'},
                        {elementName: 'Dec', color1: '#ef6d4d', height1: '55%' , color2:'rgba(241,199,103,255)' , height2: '65%'},
                    ] , 
                    [
                        {elementName: 'Jan', color1: '#ef6d4d', height1: '25%' , color2:'rgba(241,199,103,255)' , height2: '35%'},
                        {elementName: 'Feb', color1: '#ef6d4d', height1: '50%' , color2:'rgba(241,199,103,255)' , height2: '65%'},
                        {elementName: 'Mar', color1: '#ef6d4d', height1: '15%' , color2:'rgba(241,199,103,255)' , height2: '30%'},
                        {elementName: 'Apr', color1: '#ef6d4d', height1: '60%' , color2:'rgba(241,199,103,255)' , height2: '25%'},
                        {elementName: 'May', color1: '#ef6d4d', height1: '55%' , color2:'rgba(241,199,103,255)' , height2: '70%'},
                        {elementName: 'Jun', color1: '#ef6d4d', height1: '80%' , color2:'rgba(241,199,103,255)' , height2: '75%'},
                        {elementName: 'Jul', color1: '#ef6d4d', height1: '95%' , color2:'rgba(241,199,103,255)' , height2: '90%'},
                        {elementName: 'Aug', color1: '#ef6d4d', height1: '50%' , color2:'rgba(241,199,103,255)' , height2: '53%'},
                        {elementName: 'Sep', color1: '#ef6d4d', height1: '52%' , color2:'rgba(241,199,103,255)' , height2: '47%'},
                        {elementName: 'Oct', color1: '#ef6d4d', height1: '35%' , color2:'rgba(241,199,103,255)' , height2: '37%'},
                        {elementName: 'Nov', color1: '#ef6d4d', height1: '80%' , color2:'rgba(241,199,103,255)' , height2: '82%'},
                        {elementName: 'Dec', color1: '#ef6d4d', height1: '71%' , color2:'rgba(241,199,103,255)' , height2: '80%'},
                    ] , 
                ] , 
                graphchart_buttons: ['Prev Month', 'Next Month'],
                graphchart_buttonss: ['Prev Month', 'Next Month']
            };
        },
        methods: {
            handleChildValueChange(newValue) {
                this.styles = this.styles_list[newValue - 1]
                this.percent = this.percents[newValue - 1]
                this.amount = this.amounts[newValue - 1]
            }
        }
    }
</script>

<style>
    .graphchart{
        padding:30px; 
        margin: 4vh 0 ; 
        background: white; 
    }
    .graph {
        width: 700px;
        height: 250px;
        display: flex;
        flex-direction: row;
        align-items: baseline;
        justify-content: space-between;
        margin: 2%;
        background: white ; 
    }

    .graphchart__graph{
        display: flex; 
        background: white; 
    }

    .graphchart__numbers{
        margin-top: 2vh; 
    }

    .graphchart__number{
        margin-bottom: 2.7vh; 
        font-size: 14px; 
        color:  rgba(0, 0, 0, 0.7); 
    }

    .graphchart__title{
        font-family: 'Open Sans' , sans-serif ; 
        font-size: 26px ; 
        font-weight: 600 ; 
        color: navy;
    }

    .graphchart__header{
        display: flex ; 
        justify-content: space-between ; 
    }

    .graphchart__title-r{
        display: flex; 
        gap: 20px ; 
    }

    .graphchart__header-other{
        margin-top: 1vh; 
        margin-right: 20px; 
    }

    .graphchart__stats{
        margin-top: 1.5vh; 
        padding: 10px; 
    }

    .graphchart__stats-tags{
        display: flex ;
        gap: 20px ; 
    }

    .graphchart__stats-tag{
        display: flex ; 
        gap: 5px; 
        width: fit-content ; 
    }

    .graphchart__stats-tag-title{
        font-size: 14px;    
        color: rgba(0, 0, 0, 0.7);
    }

    .graphchart__stats-options{
        margin-top: 3vh; 
    }

    .graphchart__stats-option{
        margin-bottom: 1.5vh; 
    }
    
    .graphchart__stats-option-title{
        font-size: 14px;    
        color: rgba(0, 0, 0, 0.7);
    }

    .graphchart__stats-option-bottom{
        display: flex; 
    }

    .graphchart__stats-option-icon{
        margin-top: 3px; 
        margin-right: 10px; 
    }

    .graphchart__stats-option-count{
        font-family: 'Open Sans' , sans-serif ; 
        font-size: 26px ; 
        font-weight: 600 ; 
        color: navy;
        margin: 1vh 0 ; 
    }

    .graphchart__stats-option-percent{
        font-family: 'Open Sans' , sans-serif ; 
        font-size: 18px ; 
        font-weight: 600 ; 
        color: #02ba70;
    }

    .graphchart__stats-option-percentt{
        font-family: 'Open Sans' , sans-serif ; 
        font-size: 18px ; 
        font-weight: 600 ; 
        color: #ba3902;
    }

    

</style>
