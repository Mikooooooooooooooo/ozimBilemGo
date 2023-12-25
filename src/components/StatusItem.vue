<template>
    <div class="statusItem">
        <div class="statusItem-title">
            {{ title }}
        </div>
        <div class="statusItem-row" :style="{width: parseInt((height/100)*80) + '%' }">
            <div class="statusItem-row-first" :style="{background:color}" >

            </div>
            <div class="statusItem-row-second" :style="{background:color}">
                
            </div>
            <div class="statusItem-row-third" :style="{background:color}">
                
            </div>
            <div class="statusItem-row-fourth" :style="{background:color}">
                
            </div>
        </div>
    </div>
</template>

<script>
    export default{
        props:['title' , 'color' , 'height']
    }
</script>

<style>
    .statusItem {
        display: flex;
        gap: 10px;
        margin: 2vh 0 ; 
    }

    .statusItem-title{
        color: rgba(0, 0, 0, 0.7);
        font-size: 14px; 
        width: 50px ; 
    }

    .statusItem-row {
        margin-top: 5px;
        height: 10px;
        display: flex;
        border-radius: 5px; 
    }

    .statusItem-row-first {
        flex: 4;
        opacity: 0.6;
        border-radius: 5px 0 0 5px; 
    }

    .statusItem-row-second {
        flex: 3;
        opacity: 0.3;
    }

    .statusItem-row-third {
        flex: 2;
        opacity: 0.2;
    }

    .statusItem-row-fourth {
        flex: 1;
        opacity: 0.1;
        border-radius: 0 5px 5px 0 ; 
    }
</style>