<template>
    <div class="upgradebutton">
        <div class="upgradebutton__logo">
            <CircleProgress :percentage="75" />
            <div class="upgradebutton__circle">
                <div class="upgradebutton__inner-container">
                    <div class="upgradebutton__inner">

                    </div>
                </div>
            </div>
            <div class="upgradebutton__icon">
                <svg xmlns="http://www.w3.org/2000/svg" fill="#ef6d4d" height="40" width="35" viewBox="0 0 448 512"><path d="M448 80v48c0 44.2-100.3 80-224 80S0 172.2 0 128V80C0 35.8 100.3 0 224 0S448 35.8 448 80zM393.2 214.7c20.8-7.4 39.9-16.9 54.8-28.6V288c0 44.2-100.3 80-224 80S0 332.2 0 288V186.1c14.9 11.8 34 21.2 54.8 28.6C99.7 230.7 159.5 240 224 240s124.3-9.3 169.2-25.3zM0 346.1c14.9 11.8 34 21.2 54.8 28.6C99.7 390.7 159.5 400 224 400s124.3-9.3 169.2-25.3c20.8-7.4 39.9-16.9 54.8-28.6V432c0 44.2-100.3 80-224 80S0 476.2 0 432V346.1z"/></svg>
            </div>
        </div>
        <div class="upgradebutton__content">
            <div class="upgradebutton__title">
                Upgrade Your Storage
            </div>
            <div class="upgradebutton__description">
                Lorem ipsum dolor sit amet, consectetur adipisicing elit. Incidunt, ut!
            </div>
            <Button title="Upgrade" ></Button>
        </div>  
    </div>
</template>

<script>
    import Button from './Button.vue';
    import CircleProgress from './CircleProgress.vue'

    export default{
        components: {
            CircleProgress , 
            Button
        }
    }
</script>

<style>
    @import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500;600;700&family=Open+Sans:ital,wght@0,400;0,500;0,700;1,600&display=swap');

    .upgradebutton{
        padding: 30px; 
        background: white ; 
        display: flex ;
        gap: 30px; 
        font-family: 'Open Sans' , sans-serif ; 
    }
    .upgradebutton__logo{
        position: relative ; 
        width: fit-content; 
    }
    .upgradebutton__icon{
        padding: 24.5px 28px;
        position: absolute; 
        background: rgba(255, 127, 80, 0.3) ; 
        right: 19% ; 
        top: 18% ; 
        border-radius: 50% ; 
    }
    .upgradebutton__circle{
        position: absolute ;
        right: -6px; 
        top: 62px; 
        width: 30px; 
        height: 30px ; 
        border-radius: 50% ; 
        background: #ef6d4d;
    }
    .upgradebutton__inner{
        position: absolute ; 
        right: 5px; 
        top: 5px; 
        width: 20px ;
        height: 20px; 
        background: white ; 
        border-radius: 50% ;
    }
    .upgradebutton__inner-container{
        position: relative ;
    }
    .upgradebutton__title{
        font-size: 20px ; 
        font-weight: 700 ; 
        color: navy;
        margin-bottom: 1.5vh ; 
    }
    .upgradebutton__description{
        font-size: 14px;    
        color: rgba(0, 0, 0, 0.7);
        margin-bottom: 3.5vh ; 
    }
    

</style>