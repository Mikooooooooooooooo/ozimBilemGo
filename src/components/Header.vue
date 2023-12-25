<template>
    <div class="container">
        <div class="left-side">
            <AppLogo></AppLogo>
            <SearchBar></SearchBar>
        </div>

        <div class="right-side">
            <LanguageButton></LanguageButton>
            <img src="../assets/settings.png" alt="">
            <img src="../assets/megaphone.png" alt="">
            <HeaderAccount></HeaderAccount>
        </div> 
    </div>
</template>

<script>
    import AppLogo from './AppLogo.vue'
    import SearchBar from './SearchBar.vue';
    import LanguageButton from './LanguageButton.vue';
    import HeaderAccount from './HeaderAccount.vue';

    export default {
        name: 'App',
        components: {
        AppLogo,
        SearchBar,
        LanguageButton,
        HeaderAccount
        }
    }
</script>

<style>
    .container{
        width: 100%;
        height: 100px;
        display: flex;
        justify-content: space-between;
        background: white ; 
        align-items: center;
    }
    .left-side{
        display: flex;
        width: 600px;
        justify-content: space-between;

    }
    .right-side{
        display: flex;
        width: 520px;
        justify-content: space-between;
        align-items: center;
    }
    img{
        width: 20px;
        height: 20px;
    }
</style>

  
