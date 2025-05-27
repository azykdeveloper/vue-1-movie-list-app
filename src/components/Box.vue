<template>
  <div class="box">
    <slot></slot>
  </div>
</template>

<script>
  export default {
    
  }
</script>

<style  scoped>
  .box {
    box-shadow: 15px 15px 25px rgba(0, 0, 0, .05);
    border: 1px solid #e7e7e7;
    background-color: #ffefc7e6;
    padding: 1.5rem;
    border-radius: 4px;
    margin-bottom: 2rem;
  }
</style>