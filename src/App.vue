<template>
  <div class="dashboard__container">
    <Header class="dashboard__header"></Header>
    <div class="dashboard__container-inner">
      <div class="dashboard__container-left">
        <MenuBar></MenuBar>
        <UpgradeAdd></UpgradeAdd>
      </div>
      <div class="dashboard__container-content">
        <div class="dashboard__container-contenter">
          <div class="dashboard__container-mid">
            <div class="dashboard__mid-top">
              <Title title="Dashboard"></Title>
              <ChangePeriod/>
            </div>
            <GroupStata/>
            <div class="dashboard__mid-charts">
              <LineChart/> 
              <SpinChart :size="200" :percentages="[46, 47, 142,125 ]" :strokeWidth="20" />
            </div>
            <GraphChart/>
            <div class="dashboard__mid-cardbuttons">
              <UpgradeButton class="dashboard__mid-upgradebutton"/>
              <ComposeButton class="dashboard__mid-upgradebutton"></ComposeButton>
            </div>
          </div>
          <div class="dashboard__container-right">
            <Status/>
            <Contacts/>
            <ProjectC/>
          </div>
        </div>
        <Review/>
      </div>
    </div>
  </div>
</template>

<script>
  import Header from './components/Header.vue'
  import MenuBar from './components/MenuBar.vue'
  import UpgradeAdd from './components/UpgradeAdd.vue'
  import GroupStata from './components/GroupStata.vue'
  import Title from './components/Title.vue'
  import ChangePeriod from './components/ChangePeriod.vue'
  import LineChart from './components/LineChart.vue'
  import SpinChart from './components/SpinChart.vue'
  import GraphChart from './components/GraphChart.vue'
  import UpgradeButton from './components/UpgradeButton.vue'
  import ComposeButton from './components/ComposeButton.vue'
  import Status from './components/Status.vue'
  import Contacts from './components/Contacts.vue'
  import ProjectC from './components/ProjectC.vue'
  import Review from './components/Review.vue'

  export default {
      name: 'App',
      components: {
      Header,
      MenuBar , 
      UpgradeAdd , 
      GroupStata , 
      Title , 
      ChangePeriod , 
      LineChart , 
      SpinChart , 
      GraphChart , 
      UpgradeButton , 
      ComposeButton , 
      Status , 
      Contacts , 
      ProjectC  , 
      Review
      }
  }
</script>

<style>
  *{
      box-sizing: border-box;
      padding: 0;
      margin:0;
  }
  body{
      color: navy;
      font-family: Verdana, Geneva, Tahoma, sans-serif;
  }
  .dashboard__container{
    width: 97.5% ; 
    margin: 0 0 0 2.5% ; 
  }
  .dashboard__header{
    /* position: fixed ; */
  }
  .dashboard__container-inner{
    display: flex ;
  }
  .dashboard__container-left{
    padding-right: 30px ; 
  }
  .dashboard__container-content{
    background: #f5f5f5;
    width: 100% ;
  }
  .dashboard__container-contenter{
    display: flex ; 
    margin-bottom: 4vh ; 
  }
  .dashboard__container-mid{
    margin-top: 2vh ; 
    padding: 2vh 2.5% 0 ; 
    width: 75% ; 
  }
  .dashboard__mid-top{
    display: flex ; 
    width: 100% ;
    justify-content: space-between ; 
  }
  .dashboard__mid-charts{
    display: flex ; 
    gap: 40px; 
  }
  .dashboard__mid-cardbuttons{
    display: flex ; 
    justify-content: space-between;
  }
  .dashboard__mid-upgradebutton{
    width: 48.2% ; 
  }
  .dashboard__container-right{
    width: 22.5% ;
  }
  
</style>
