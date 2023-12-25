<template>  
    <div class="contactItem">
        <div class="contactItem-r">
            <div class="contactItem-icon">
                <img :src="imageSrc" alt="">
            </div>
            <div class="contactItem-text">
                <div class="contactItem-name">
                    {{ job }}
                </div>
                <div class="contactItem-job">
                    {{ name}}
                </div>
            </div>
        </div>
        <div class="contactItem-message">
            <img v-if="!isHave"  src="../assets/envelope.svg" alt="" class="contactItem-message-icon">
            <Notification v-else>
                <img  src="../assets/envelope.svg" alt="" class="">
            </Notification>
        </div>
    </div>
</template>

<script>
    import Notification from './Notification.vue'
    export default{ 
        props: ['name' , 'iconSrc' , 'job' , 'isHave'] ,
        data () {
            return {
                imageSrc: require("../assets/" + this.iconSrc)
            }
        } , 
        components: {
            Notification
        }
    }
</script>

<style>
    @import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500;600;700&family=Open+Sans:ital,wght@0,400;0,500;0,700;1,600&display=swap');

    .contactItem{
        display: flex; 
        justify-content: space-between;
        font-family: 'Open Sans' , sans-serif ;
        margin: 1vh 0 ; 
    }
    .contactItem-icon{
        margin-right: 10px; 
    }
    .contactItem-r{
        display: flex; 
    }
    .contactItem-icon img{
        width: 40px; 
        height: 40px; 
        object-fit: cover;
    }
    .contactItem-name{
        font-weight: 700 ; 
        font-size: 14px; 
        color: navy;
    }
    .contactItem-job{
        font-size: 14px;    
        color: rgba(0, 0, 0, 0.7);
    }
    .contactItem-message-icon{
        margin-right: 15px; 
        margin-top: 10px ; 
    }

</style>