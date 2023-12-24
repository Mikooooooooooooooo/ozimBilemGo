<template>
    <div class="circle-progress">
      <svg :width="size" :height="size" xmlns="http://www.w3.org/2000/svg">
        <circle
          :cx="radius"
          :cy="radius"
          :r="radius - strokeWidth / 2"
          :stroke="baseColor"
          :stroke-width="strokeWidth"
          fill="none"
        />
        <circle
          :cx="radius"
          :cy="radius"
          :r="radius - strokeWidth / 2"
          :stroke="progressColor"
          :stroke-width="strokeWidth"
          :stroke-dasharray="circumference"
          :stroke-dashoffset="dashoffset"
          fill="none"
          transform="rotate(90, radius, radius)"
        />
      </svg>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      percentage: {
        type: Number,
        required: true,
        validator: (value) => value >= 0 && value <= 100,
      },
      size: {
        type: Number,
        default: 150,
      },
      strokeWidth: {
        type: Number,
        default: 17,
      },
      baseColor: {
        type: String,
        default: '#e0e0e0',
      },
      progressColor: {
        type: String,
        default: 'rgba(241,199,103,255)',
      },
    },
    computed: {
      radius() {
        return this.size / 2;
      },
      circumference() {
        return 2 * Math.PI * (this.radius - this.strokeWidth / 2);
      },
      dashoffset() {
        // return this.circumference * (1 - this.percentage / 45);
        return -150; 
      },
    },
  };
  </script>
  
  <style scoped>
  .circle-progress {
    display: inline-block;
  }
  </style>
  