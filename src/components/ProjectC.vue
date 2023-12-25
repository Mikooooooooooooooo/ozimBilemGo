<template>
    <div class="projectC">
        <div class="projectC__header">
            <div class="projectC__title">
                Project
            </div>
            <img src="../assets/other.svg" alt="" class="projectC__other">
        </div>
        <div class="projectC__progresses">
            <Progress width="65%" color="#8f5eeb"></Progress>
            <div class="projectC__progresses-text">
                <div class="projectC__progresses-title">
                    Web Design
                </div>
                <div class="projectC__progresses-count">
                    452 times 
                </div>
            </div>
            <Progress width="40%" color="#ef6d4d"></Progress>
            <div class="projectC__progresses-text">
                <div class="projectC__progresses-title">
                    Graphic Design
                </div>
                <div class="projectC__progresses-count">
                    97 times 
                </div>
            </div>
            <Progress width="65%" color="#0283ba"></Progress>
            <div class="projectC__progresses-text">
                <div class="projectC__progresses-title">
                    Front-End 
                </div>
                <div class="projectC__progresses-count">
                    61 times 
                </div>
            </div>
        </div>
        <div class="projectC__tags">
            <div class="projectC__tags-intro">
                Tag
            </div>
            <div class="projectC__tags-block">
                <Tag title="#teamwork" />
                <Tag title="#design" />
            </div>
            <div class="projectC__tags-block">
                <Tag title="#projectmanagement" />
                <Tag title="16+" />
            </div>
        </div>
        
    </div>
</template>

<script>
    import Progress from './Progress.vue'
    import Tag from './Tag.vue';

    export default{
        components:{
            Progress , 
            Tag
        }
    }
</script>

<style>
    @import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500;600;700&family=Open+Sans:ital,wght@0,400;0,500;0,700;1,600&display=swap');

    .projectC{
        padding:30px; 
        background: white ; 
        font-family: 'Open Sans' , sans-serif ; 
    }
    .projectC__header{
        display: flex; 
        justify-content: space-between ; 
        margin-bottom: 3vh ; 
    }
    .projectC__title{
        font-size: 24px ; 
        font-weight: 600 ; 
        color: navy;
    }
    .projectC__other{
        margin-top: 10px; 
    }
    .projectC__progresses{
        width: 90% ;
    }
    .projectC__progresses-text{
        display: flex; 
        justify-content: space-between;
        margin-bottom: 3.5vh ; 
        margin-top: 10px; 
    }
    .projectC__progresses-title{
        font-size: 14px ; 
        font-weight: 600 ; 
        color: navy;
    }
    .projectC__progresses-count{
        font-size: 14px;    
        color: rgba(0, 0, 0, 0.7);
    }
    .projectC__tags-intro{
        color: rgba(0, 0, 0, 0.7);
        font-size: 22px; 
        margin: 4vh 0 ; 
    }
    .projectC__tags-block{
        display: flex; 
        gap: 10px; 
        margin: 1vh 0 ;
    }
</style>