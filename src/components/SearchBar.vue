<template>
    <div class="search-bar">
      <img src="../assets/search.png" alt="">   
      <input type="text" placeholder="Search here..." />
    </div>
  </template>
  
  <style scoped>
  .search-bar {
    display: flex;
    align-items: center;
    padding: 14px;
    background-color: rgba(45, 43, 65, 0.03);
    width: 300px;
    height: 40px;
  }
  
  .search-bar input {
    border: 0;
    padding-left: 10px;
    font-size: 12px;
    background-color: transparent;
    font-family: Verdana, Geneva, Tahoma, sans-serif;
  }
  
  .search-bar img {
    width: 29px;
    height: 20px;
    padding-right: 5px;
    padding-left: 5px;
  }
  </style>
  