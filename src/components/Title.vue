<template>
    <div class="logo">
      <h1>{{ title }}</h1>
    </div>
</template>

<script>
export default {
    props: ['title']
}
</script>
  
<style scoped>
  .logo {
      font-size: 14px;
      font-weight: 500;
      font-family: Verdana, Geneva, Tahoma, sans-serif;
      color: navy;
  }
  
</style>
  