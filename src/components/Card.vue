<template>
    <div class="card">
        <div class="card__header">
            <img :src="getSource()" alt="" class="card__icon">
            <div class="card__text">
                <div class="card__name">
                    {{ item.name }}
                </div>
                <div class="card__bottom">
                    <div class="card__job">
                        {{ item.job }}
                    </div>
                    <img src="../assets/star.svg" alt="" class="card__rate-icon">
                    <div class="card__rate-value">
                        {{ item.value }}
                    </div>
                </div>
            </div>
        </div>
        <div class="card__description">
            {{ item.description }}
        </div>
    </div>
</template>

<script>
    export default{
        props: ['item'] , 
        data() {
            return {
                imageSrc: require("../assets/" + this.item.source)
            }
        } , 
        methods : { 
            getSource(){
                return require("../assets/" + this.item.source) ; 
            }
        }
    }
</script>

<style>
    @import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500;600;700&family=Open+Sans:ital,wght@0,400;0,500;0,700;1,600&display=swap');

    .card{
        width: 30% ; 
        background: white; 
        padding: 30px; 
        font-family: 'Open Sans' , sans-serif ; 
    }
    .card__header{
        display: flex; 
        gap: 15px; 
        margin-bottom: 2vh ; 
    }
    .card__name{
        color: navy;
        font-size: 16px; 
        font-weight: 600; 
        margin-bottom: 5px; 
    }
    .card__bottom{
        display: flex ; 
        color: rgba(0, 0, 0, 0.7);
        font-size: 14px; 
    }
    .card__description{
        color: navy ; 
        font-size: 14px; 
        font-weight: 500 ;
    }
    .card__icon{
        width: 50px; 
        height: 50px; 
        object-fit: cover;
    }
    .card__rate-icon{
        margin: 0 8px; 
    }
</style>