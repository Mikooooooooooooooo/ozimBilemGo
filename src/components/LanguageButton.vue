<template>
    <div class="change-language">
        <img src="../assets/usa.png" alt="">
        <p>English (US)</p>
        <img src="../assets/down.png" alt="">
    </div>
</template>

<script>
export default {
  name: 'ChangeLanguage'
}
</script>
    
<style scoped>
    .change-language img{
        width: 15px;
        height: 15px;
    }
    .change-language{
        width:170px;
        height: 40px;
        border: 1px solid rgba(0, 0, 0, 0.1);
        font-weight: 600;
        display: flex;
        align-items: center;
        padding: 14px;
        font-size: 10px;
        justify-content: center;
    }
    .change-language p{
        padding: 0 10px 0 10px;
        font-size: 12px;
    }
    
</style>
  