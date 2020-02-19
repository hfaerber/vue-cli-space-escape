<template>
  <section class='daily-container'>
    <header class='daily-header'>
      <p>{{ image.title }}</p>
      <p>{{ image.date }}</p>
    </header>
    <img class='image' :src="image.url" />
  </section>
</template>

<script>
  export default {
    name: 'Daily',
    props: ['image'],

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
  .image {
  border: 1px ridge whitesmoke;
  width: 100%;
}
</style>
