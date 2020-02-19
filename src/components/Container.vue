<template>
  <main class="main" id='main'>
    <h3 class='error-message' v-if="error">
      Uh-oh. The data seems to be lost in space.</h3>
    <Daily
      v-for="image in images"
      v-bind:key="image.date"
      v-bind:image="image" />
  </main>
</template>

<script>
import Daily from './Daily.vue'
  export default {
    name: 'Container',
    components: {
      Daily
    },
    data() {
      return {
      api: 'jq2n1ETd4APk53HUGfnypIpPwz7Q84Q6CjJAbjiT',
      images: [],
      error: false,
      };
    },
    created: function() {
      this.getDailyImages(this.api, this.findStartDate())
      .then(data => {
        this.images = this.cleanData(data).reverse();
        console.log(this.images)
      })
      .catch(() => this.error = true)
    },
    methods: {
      cleanData: (data) => {
        return data.map(day => {
          return {
            date: day.date,
            url: day.url,
            title: day.title,
            explanation: day.explanation,
            copyright: day.copyright ? day.copyright : null
          }
        })
      },
      getDailyImages: async (api, date) => {
        const url = date ?
        `https://api.nasa.gov/planetary/apod?api_key=${api}&start_date=${date}` :
        `https://api.nasa.gov/planetary/apod?api_key=${api}`;
        const response = await fetch(url);
        if(!response.ok) {
          throw new Error('Something went wrong')
        }
        const imageData = await response.json();
        return imageData
      },
      findStartDate: () => {
        let today = new Date();
        let mm = today.getMonth() + 1;
        let yyyy = today.getFullYear();
        if (mm < 10) {
          mm = `0${mm}`;
        }
        return `${yyyy}-${mm}-01`
      },
      goToToday: () => {
        document.body.scrollTop = 0;
        document.documentElement.scrollTop = 0;
      }
    },
  }
</script>

<style>
  .error-message {
    color: red;
    font-size: 2em;
    line-height: 3;
    background: rgba(0, 0, 0, 0.5);
    text-align: center;
  }
</style>
