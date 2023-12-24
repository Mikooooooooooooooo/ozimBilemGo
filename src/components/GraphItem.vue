<template>
    <div class="graphItem">
      <div class="graphItem-element">
        <div :style="{ height: height1, background: color1 }" class="graphItem-l"></div>
        <div :style="{ height: height2, background: color2 }" class="graphItem-l"></div>
      </div>
      <label for="graphItem-element" class="graphItem-label">{{ title }}</label>
    </div>
  </template>
  
  <script>
  export default {
    props: ['title', 'height1', 'color1', 'height2', 'color2']
  };
  </script>
  
  <style>
  .graphItem {
    display: flex;
    flex-direction: column;
    align-items: center;
    height: 100%;
    margin-right: 10px; 
  }
  
  .graphItem-element {
    width: 40px;
    height: 100%;
    display: flex;
    flex-direction: row;
    gap: 10%;
    align-items: flex-end; /* Align items to the bottom */
  }
  
  .graphItem-l {
    width: 40%;
  }
  
  .graphItem-label {
    margin-top: 10px;
  }
  </style>
  