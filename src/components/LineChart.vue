<template>
    <div class="line__chart">

      <div class="line__chart-header">
        <div class="line__chart-title">
            Project Statistics
        </div>
        <div class="line__chart-header-r">
          <Dropdawn titlee="This Month" @click="handleChildValueChange" :buttons="dropdawn_buttons" :buttonss="dropdawn_buttonss" />
          <img src="../assets/other.svg" class="line__chart-header-other" alt="">
        </div>
      </div>

      <div class="line__chart-stats">
        <div class="line__chart-stats-l">
          <div class="line__chart-stats-box">
            <div class="line__chart-stats-icon">
              <svg xmlns="http://www.w3.org/2000/svg" height="12"  width="12" fill="#ebbe5e" viewBox="0 0 512 512"><path  d="M464 256A208 208 0 1 0 48 256a208 208 0 1 0 416 0zM0 256a256 256 0 1 1 512 0A256 256 0 1 1 0 256z"/></svg>
            </div>
            <div class="line__chart__stats-text">
              <div class="line__chart-stats-title">
                This Week
              </div>
              <div class="line__chart-stats-count">
                {{ count1 }}
              </div>
            </div>
          </div>
          <div class="line__chart-stats-box">
            <div class="line__chart-stats-icon">
              <svg xmlns="http://www.w3.org/2000/svg" height="12"  width="12" fill="#e07502" viewBox="0 0 512 512"><path  d="M464 256A208 208 0 1 0 48 256a208 208 0 1 0 416 0zM0 256a256 256 0 1 1 512 0A256 256 0 1 1 0 256z"/></svg>
            </div>
            <div class="line__chart__stats-text">
              <div class="line__chart-stats-title">
                This Week
              </div>
              <div class="line__chart-stats-count">
                {{ count2 }}
              </div>
            </div>
          </div>
        </div>
        <div class="line__chart-stats-total">
          <div class="line__chart-stats-total-top">
            <div class="line__chart-stats-total-title">
              Total
            </div>
            <div class="line__chart-stats-total-count">
              {{ total }}
            </div>    
          </div>
          <Progress :width="percent" color="#e07502"> </Progress>
        </div>
      </div>

    <div class="line-chart">
      <div class="line-chart-top">
        <div class="line-chart-y">
            <div class="line-chart-yItem">
                100
            </div>
            <div class="line-chart-yItem">
                80
            </div>
            <div class="line-chart-yItem">
                60
            </div>
            <div class="line-chart-yItem">
                40
            </div>
            <div class="line-chart-yItem">
                20
            </div>
            <div class="line-chart-yItem">
                0
            </div>
        </div>
        <svg :width="width" :height="height" class="line-chart-graph">

        <polyline
            :points="getLinePoints(chartData1)"
            fill="none"
            stroke="#ebbe5e"  
            stroke-width="4"
            stroke-linecap="round"
        />

        <polyline
            :points="getLinePoints(chartData2)"
            fill="none"
            stroke="#e07502" 
            stroke-width="4"
            stroke-linejoin="round" 
        />
        </svg>
      </div>
      <div class="line-chart-x">
        <div class="line-chart-xItem">
            Mon
            <div class="line-chart-col">

            </div>
        </div>
        <div class="line-chart-xItem">
            Tue
            <div class="line-chart-col">
                
            </div>
        </div>
        <div class="line-chart-xItem">
            Wed
            <div class="line-chart-col">
                
            </div>
        </div>
        <div class="line-chart-xItem">
            Thu
            <div class="line-chart-col">
                
            </div>
        </div>
        <div class="line-chart-xItem">
            Fri
            <div class="line-chart-col">
                
            </div>
        </div>
        <div class="line-chart-xItem">
            Sat
            <div class="line-chart-col">
                
            </div>
        </div>
        <div class="line-chart-xItem">
            Sun
            <div class="line-chart-col">
                
            </div>
        </div>

      </div>
     
    </div>
    </div>

  </template>
  
<script>
import Dropdawn from './Dropdawn.vue';
import Progress from './Progress.vue';

export default {
  data() {
    return {
      width: 550,
      height: 200,
      type: 1,
      count1: '1,982' , 
      count2: '1,345', 
      total: '3,982' , 
      percent: '65%' ,
      counts1: ['1,982' , '2,032' , '1,677'] , 
      counts2: ['1,345' , '1,556' , '1,995'] , 
      totals: ['3,982' , '4,322' , '4,446' ] , 
      percents: ['65%' , '73%' , '75%'] , 
      charts1: [[{ x: 0, y: 2 },
          { x: 1, y: 2 },
          { x: 2, y: 4 },
          { x: 3, y: 2 },
          { x: 4, y: 6 },
          { x: 5, y: 5 },
          { x: 6, y: 5 },] , 
          [{ x: 0, y: 4 },
          { x: 1, y: 7 },
          { x: 2, y: 8 },
          { x: 3, y: 5 },
          { x: 4, y: 3 },
          { x: 5, y: 2 },
          { x: 6, y: 6 },] , 
          [{ x: 0, y: 8 },
          { x: 1, y: 7 },
          { x: 2, y: 5 },
          { x: 3, y: 7 },
          { x: 4, y: 2 },
          { x: 5, y: 4 },
          { x: 6, y: 6 },]
     ] , 
      charts2: [
      [{ x: 0, y: 4 },
          { x: 1, y: 4 },
          { x: 2, y: 5 },
          { x: 3, y: 6 },
          { x: 4, y: 5 },
          { x: 5, y: 3 },
          { x: 6, y: 2 },] , 
          [{ x: 0, y: 8 },
          { x: 1, y: 7 },
          { x: 2, y: 5 },
          { x: 3, y: 7 },
          { x: 4, y: 2 },
          { x: 5, y: 4 },
          { x: 6, y: 6 },] ,
          [{ x: 0, y: 2 },
          { x: 1, y: 2 },
          { x: 2, y: 4 },
          { x: 3, y: 2 },
          { x: 4, y: 6 },
          { x: 5, y: 5 },
          { x: 6, y: 5 },] 
        ]
      ,
      chartData1: [],
      chartData2: [],
      dropdawn_buttons: ['Prev Month', 'Next Month'],
      dropdawn_buttonss: ['Prev Month', 'Next Month'],
    };
  },
  computed: {
    maxX() {
      const allData = this.chartData1.concat(this.chartData2);
      return Math.max(...allData.map(point => point.x), 0);
    },
    maxY() {
      const allData = this.chartData1.concat(this.chartData2);
      return Math.max(...allData.map(point => point.y), 0);
    },
  },
  methods: {
    getLinePoints(data) {
      return data
        .map(point => `${(point.x / this.maxX) * this.width},${this.height - (point.y / this.maxY) * this.height}`)
        .join(' ');
    },
    handleChildValueChange(newValue) {
      this.type = newValue;
      this.chartData1 = this.charts1[this.type-1];
      this.chartData2 = this.charts2[this.type-1];
      this.count1 = this.counts1[this.type-1] ;
      this.count2 = this.counts2[this.type-1] ; 
      this.percent = this.percents[this.type-1] ; 
      this.total = this.totals[this.type-1] ; 
    },
  },
  created() {
    this.chartData1 = this.charts1[0];
    this.chartData2 = this.charts2[0];
  },
  components: {
    Dropdawn,
    Progress
  },
};
</script>

  
  <style scoped>

  @import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500;600;700&family=Open+Sans:ital,wght@0,400;0,500;0,700;1,600&display=swap');

  .line__chart{
    width: 65% ; 
    padding: 20px 40px 0; 
    background: white ; 
    font-family: 'Open Sans' , sans-serif ; 
  }

  .line__chart-header{
    display: flex; 
    justify-content: space-between ;
  }

  .line__chart-header-r{
    display: flex ;
    gap: 20px; 
  }

  .line__chart-header-other{
    margin-top: 10px ;
    margin-right: 20px;  
  }

  .line-chart-graph{
    position: relative ; 
    bottom: -100px ;
    left: 7px; 
  }

  .line__chart-title{
      font-size: 23px;
      font-weight: 600;
      font-family: 'Open Sans' , sans-serif ; 
      color: navy;
  }

  .line__chart-stats{
    margin: 2vh 0; 
    display: flex ; 
    justify-content: space-between ; 
  }

  .line__chart-stats-box{
    display: flex; 
  }

  .line__chart-stats-icon{
    margin-right: 10px; 
  }
  .line__chart-stats-title{
    font-size: 13px ; 
    color: rgba(0, 0, 0, 0.7); 
  }

  .line__chart-stats-count{
    font-size: 18px ; 
    font-weight: 600 ; 
    color: navy;
    padding-bottom: 1vh;
  }

  .line__chart-stats-l{
    display: flex ; 
    gap: 20px ; 
  }

  .line__chart-stats-total{
    width: 160px; 
    margin-right: 20px; 
  }
  .line__chart-stats-total-top{
    display: flex ; 
    justify-content: space-between ; 
  }
  .line__chart-stats-total-title{
    color: rgba(0, 0, 0, 0.7);
    font-size: 14px; 
  }
  .line__chart-stats-total-count{
    font-size: 18px ; 
    font-weight: 700 ; 
    color: navy;
  }
  .line-chart {
    display: inline-block;
    margin: 20px 20px 0 ;
  }

  .line-chart-y{
    padding-top: 1vh ; 
  }

  .line-chart-yItem{
    padding-bottom: 3vh ; 
  }

  .line-chart-top{
    display: flex ;
  }

  .line-chart-x{
    position: relative ; 
    top: -30px ;
    margin-left: 20px; 
    gap: 60px; 
    display: flex ;
  }

  .line-chart-xItem{
    position: relative ;
  }

  .line-chart-col{
    left: 17px ; 
    height:250px; 
    width: 1px; 
    background: gray ;
    position: absolute; 
    top: -250px ;
  }

  </style>
  