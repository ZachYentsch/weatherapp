<template>
  <nav>
  </nav>
  <router-view/>
</template>

<script>
import { axios } from 'axios'

export default defineComponent({
  name: "App",
  data() {
    return {
      APIkey: "71909f05dd05f8574071e4e65a030612",
      city: "Portland"
    }
  },
  created() {
    this.getCurrentWeather();
  },
  methods: {
    getCurrentWeather() {
      axios.get(`https://api.openweathermap.org/data/2.5/weather?q=${this.city}&units=imperial&appid=${this.APIkey}`).then(res) => {
      console.log(res.data)
    }
  }
  }
})
</script>


<style lang="scss">
#app {
  font-family: "Poppins", Arial, sans-serif;
  margin: 0%;
  padding: 0%;
  box-sizing: border-box;
}


</style>
