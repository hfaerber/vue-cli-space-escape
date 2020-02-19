<template>
  <section class='daily-container'>
    <header class='daily-header'>
      <p>title will go here</p>
      <p>date will go here</p>
    </header>
    <p>image will go here</p>
  </section>
</template>

<script>
  export default {
    name: 'Daily',
  }
</script>

<style scoped>
  .daily-container {
    margin-bottom: 1%;
    margin-left: auto;
    margin-right: auto;
    width: 65%;
  }
  .daily-header {
    background: rgba(0, 0, 0, 0.5);
    display: flex;
    color: whitesmoke;
    font-size: 1.3em;
    justify-content: space-between;
    line-height: 0;
    margin-left: auto;
    margin-right: auto;
    text-align: center;
    width: 95%;
  }
</style>
