<template>
    <div class="line__chart">

        <div class="line__chart-title">
            Project Statistics
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
        <svg :width="width" :height="height">

        <polyline
            :points="getLinePoints(chartData1)"
            fill="none"
            stroke="#3498db"  
            stroke-width="4"
            stroke-linecap="round"
        />

        <polyline
            :points="getLinePoints(chartData2)"
            fill="none"
            stroke="#e74c3c" 
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
  export default {
    data() {
      return {
        width: 270,
        height: 200,
        chartData1: [
          { x: 0, y: 2 },
          { x: 1, y: 2 },
          { x: 2, y: 4 },
          { x: 3, y: 2 },
          { x: 4, y: 6 },
          { x: 5, y: 5 },
          { x: 6, y: 5 },


        ],
        chartData2: [
          { x: 0, y: 4 },
          { x: 1, y: 4 },
          { x: 2, y: 5 },
          { x: 3, y: 6 },
          { x: 4, y: 5 },
          { x: 5, y: 3 },
          { x: 6, y: 2 },
        ],
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
    },
  };
  </script>
  
  <style scoped>

  @import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500;600;700&family=Open+Sans:ital,wght@0,400;0,500;0,700;1,600&display=swap');

  .line__chart{
    width: 60% ; 
    padding: 20px; 
    background: white ; 
  }

  .line__chart-title{
      font-size: 23px;
      font-weight: 600;
      font-family: 'Open Sans' , sans-serif ; 
      color: navy;
  }

  .line-chart {
    display: inline-block;
    margin: 20px;
  }

  .line-chart-y{
    padding-top: 1vh ; 
  }

  .line-chart-yItem{
    padding-bottom: 1vh ; 
  }

  .line-chart-top{
    display: flex ;
  }

  .line-chart-x{
    position: relative ; 
    top: -30px ;
    margin-left: 20px; 
    gap: 15px; 
    display: flex ;
  }

  .line-chart-xItem{
    position: relative ;
  }

  .line-chart-col{
    left: 17px ; 
    height: 150px; 
    width: 1px; 
    background: gray ;
    position: absolute; 
    top: -150px ;
  }

  </style>
  