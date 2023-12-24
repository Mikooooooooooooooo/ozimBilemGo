<template> 
   <div class="upgrade__add">
        <div class="upgrade__title">
            Upgrade your Account to Pro
        </div>
        <div class="upgrade__button">
            Upgrade
        </div>
   </div>
</template>

<style>

    @import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500;600;700&family=Open+Sans:ital,wght@0,400;0,500;0,700;1,600&display=swap');


    .upgrade__add{
        margin-top: 6vh ; 
        width: 180px ; 
        padding: 20px ; 
        background: url('../assets/upgrade__add-background.jpg') ; 
        background-size: cover ; 
        background-position: center ; 
    }
    .upgrade__title{
        width: 130px ; 
        padding-bottom: 1vh ; 
        font-size: 14px ; 
        font-family: 'Montserrat', sans-serif;
        font-weight: 600;
        color: white ; 
    }
    .upgrade__button{
        padding: 10px 15px ;
        font-family: 'Montserrat', sans-serif;
        font-weight: 600 ; 
        font-size: 13px ; 
        color: black ; 
        background: white ; 
        width: fit-content ; 
    }
    .upgrade__button:hover{
        background: #f0f2f0 ; 
        cursor: pointer ; 
    }
</style>