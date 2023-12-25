<template>
    <div class="notification">
        <div class="notification__inner">
            <slot></slot>
            <div class="notification__circle">

            </div>
        </div>
    </div>
</template>

<style>
    .notification__inner{
        position: relative; 
        padding: 10px 15px; 
        background: rgba(255, 127, 80, 0.3) ; 
    }
    .notification__circle{
        position: absolute ;
        background:  #ef6d4d; 
        width: 13px; 
        height: 13px; 
        right: -7px; 
        top: -7px; 
        border-radius: 50%; 
    }   
</style>