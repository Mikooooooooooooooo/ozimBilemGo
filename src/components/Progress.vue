<template> 
    <div class="progress">
        <div class="progress__line" :style="{ width: width, background: color }">

        </div>
    </div>
</template>

<script>
export default {
    props: ['color', 'width']
}
</script>

<style>
.progress {
    margin-top: 1vh ; 
    background: #dedede;
    height: 10px;
}

.progress__line {
    height: 100%;
}
</style>
