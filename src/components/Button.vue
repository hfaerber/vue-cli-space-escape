<template>
  <button onclick="goToToday()" id="top-button" title="today">Back To Today</button>
</template>

<script>
  export default {
    name: 'Button',
    data() {
      return {
        topbutton: document.getElementById("top-button")
      }
    },
    created: function() {
      window.onscroll = this.scrollFunction();
    },
    methods: {
      goToToday: () => {
        document.body.scrollTop = 0;
        document.documentElement.scrollTop = 0;
      },
      scrollFunction() {
        if (document.body.scrollTop > 200 || document.documentElement.scrollTop > 200) {
          this.topbutton.style.display = "block";
        } else {
          this.topbutton.style.display = "none";
        }
      }
    }
  }
</script>

<style>
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
