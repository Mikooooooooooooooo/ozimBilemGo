<template> 
    <div class="slidecontainer">
    <input type="range" min="1" max="100" value="50" class="slider" id="myRange">
    </div>
</template> 

<style>
    .slidecontainer {
    width: 100%; 
    }

    .slider {
    appearance: none;
    width: 100%; 
    height: 25px;
    background: #d3d3d3; 
    outline: none; 
    opacity: 0.7; 
    transition: opacity .2s;
    }

    .slider:hover {
    opacity: 1; 
    }
</style>