<template>
  <div id="app">
    <header class="header">
      <h1> Space Escape</h1> <h2 class='italic'>Take a break from the noise.</h2>
    </header>
    <Container />

  </div>
</template>

<script>
import Container from './components/Container.vue'

export default {
  name: 'app',
  components: {
    Container
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.header {
  background: rgba(0, 0, 0, 0.5);
  color: whitesmoke;
  display: flex;
  justify-content: space-between;
  padding: 0 2%;
  text-align: center;
}
.italic {
  font-style: italic;
}

#top-button {
  display: none;
  position: fixed;
  bottom: 2%;
  right: 2%;
  z-index: 99;
  border: none;
  outline: none;
  background-color: whitesmoke;
  color: #0a0d1a;
  cursor: pointer;
  padding: 4px 6px;
  border-radius: 4px;
  font-size: 1.1em;
}
#top-button:hover {
  transform: scale(1.1);
}
</style>
