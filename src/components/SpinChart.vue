<template>
    <div class="donut__chart">
        <div class="donut__chart-header">
            <div class="donut__chart-title">
                Email
            </div>
            <img src="../assets/other.svg" alt="" class="donut__chart-icon">
        </div>
        <div class="donut-chart">
        <svg :width="size" :height="size">
            <g :transform="`translate(${radius}, ${radius})`">
            <circle :r="radius" fill="#f5f5f5"></circle>
            <path
                v-for="(percentage, index) in percentages"
                :key="index"
                :d="getSlicePath(index)"
                :fill="getSegmentColor(index)"
                @mouseover="handleMouseOver(index)"
                @mouseleave="handleMouseLeave"
            ></path>
            </g>
            <text
            v-if="hoveredIndex !== null"
            :x="radius"
            :y="radius"
            text-anchor="middle"
            dominant-baseline="middle"
            fill="#000"
            font-size="16"
            font-weight="bold"
            >
            {{parseInt((percentages[hoveredIndex]/360)*100) }}%
            </text>
        </svg>
        </div>
        <div class="donut__chart-options">
            <div class="donut__chart-options-title">
                Legend
            </div>
            <Option v-for="item in items" :color="item.color" :title="item.title" :count="item.count"> </Option>
        </div>
    </div>
  </template>
  
  <script>
  import Option from './Option.vue';
  export default {
    props: {
      size: { type: Number, default: 200 },
      percentages: { type: Array, default: () => [] },
      innerRadiusRatio: { type: Number, default: 0.6 },
    },
    data() {
      return {
        hoveredIndex: null,
        items: [
            {color:'#8f5eeb' , title:'Primary (27%)' , count:'763' },
            {color:'navy' , title:'Promotion (11%)' , count:'321' },
            {color:'#e07502' , title:'Forum (22%)' , count:'69' },
            {color:'#ebbe5e' , title:'Socials (15%)' , count:'154' },

        ]
      };
    },
    computed: {
      radius() {
        return this.size / 2;
      },
      innerRadius() {
        return this.radius * this.innerRadiusRatio;
      },
    },
    components: {
        Option
    },
    methods: {
      getSlicePath(index) {
        const startAngle = this.getStartAngle(index);
        const endAngle = this.getEndAngle(index);
  
        // Convert polar coordinates to Cartesian coordinates
        const x1 = this.radius * Math.cos((startAngle * Math.PI) / 180);
        const y1 = this.radius * Math.sin((startAngle * Math.PI) / 180);
        const x2 = this.radius * Math.cos((endAngle * Math.PI) / 180);
        const y2 = this.radius * Math.sin((endAngle * Math.PI) / 180);
  
        // Convert polar coordinates to Cartesian coordinates for inner radius
        const innerX1 = this.innerRadius * Math.cos((startAngle * Math.PI) / 180);
        const innerY1 = this.innerRadius * Math.sin((startAngle * Math.PI) / 180);
        const innerX2 = this.innerRadius * Math.cos((endAngle * Math.PI) / 180);
        const innerY2 = this.innerRadius * Math.sin((endAngle * Math.PI) / 180);
  
        // Arc flag to determine if the angle is more than 180 degrees
        const largeArcFlag = endAngle - startAngle <= 180 ? '0' : '1';
  
        // Create a path for both outer and inner circles to create a donut
        return `M ${innerX1} ${innerY1} A ${this.innerRadius} ${this.innerRadius} 0 ${largeArcFlag} 1 ${innerX2} ${innerY2} L ${x2} ${y2} A ${this.radius} ${this.radius} 0 ${largeArcFlag} 0 ${x1} ${y1} Z`;
      },
      getStartAngle(index) {
        return this.getAngleSum(index - 1);
      },
      getEndAngle(index) {
        return this.getAngleSum(index);
      },
      getAngle(index) {
        return (this.percentages[index] / 100) * 360;
      },
      getAngleSum(index) {
        return index >= 0
          ? this.percentages.slice(0, index + 1).reduce((acc, val) => acc + val, 0)
          : 0;
      },
      getSegmentColor(index) {
        const colors = ['navy', '#ededed', '#e07502', '#ebbe5e'];
        return colors[index % colors.length];
      },
      handleMouseOver(index) {
        this.hoveredIndex = index;
      },
      handleMouseLeave() {
        this.hoveredIndex = null;
      },
    },
  };
  </script>
  
  <style scoped>
  @import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500;600;700&family=Open+Sans:ital,wght@0,400;0,500;0,700;1,600&display=swap');
  
  .donut__chart{
    width: 100%; 
    padding: 20px 40px 0 ; 
    background: white ;
  }
  .donut__chart-header{
    display: flex; 
    justify-content: space-between;
  }
  .donut__chart-icon{
    margin-top: 10px ; 
  }
  .donut__chart-title{
      font-weight: 600;
      font-size: 22px; 
      font-family: 'Open Sans' , sans-serif ; 
      color: navy;
  }
  .donut__chart-options-title{
    font-size: 14px;    
    color: rgba(0, 0, 0, 0.7);
  }
  .donut-chart {
    display: inline-block;
    width: 100%; 
    cursor: pointer;
    text-align: center ;
    margin: 3vh 0; 
  }
  
  /* Add transition for a smooth effect */
  .donut-chart path {
    transition: fill 0.3s ease-in-out;
  }
  </style>
  