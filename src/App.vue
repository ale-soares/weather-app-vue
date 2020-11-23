<template>
  <div id="app">
    <h1>{{title}}</h1>
    <Form @fetchData="getWeather" />
    <Loader v-if="loading" />
    <Card v-bind:temperature="temperature" v-bind:icon="icon" v-else-if="!loading && showCard" />
  </div>
</template>

<script>
import Card from './components/Card'
import Form from './components/Form'
import Loader from './components/Loader'

export default {
  name: 'App',
  components: {
    Card,
    Form,
    Loader,
  },
  data() {
    return {
      title: 'Vue Weather App',
      temperature: '',
      icon: '',
      showCard: false,
      loading: false,
      weatherData: {}
    }
  },
  methods: {
        async getWeather(city) {
            try {
                this.loading = true;
                const response = await fetch(
                `https://api.openweathermap.org/data/2.5/weather?q=${city}&units=metric&appid=ce7201d8348f6361c51c87e0ea6496d4`
                );
                this.weatherData = await response.json();
                this.temperature = `${Math.round(this.weatherData.main.temp)}°C`;
                this.icon = this.weatherData.weather[0].icon;
                this.showCard = true;
            } catch (err) {
                console.log(err);
                this.showCard = false;
            } finally {
                this.loading = false;
            } 
        }
    },
}
</script>

<style>
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

  body {
    background: lightblue;
    font-family: 'Montserrat', sans-serif;
  }

  #app {
    text-align: center;
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-top: 5%;
  }

  #app h1 {
    color: darkcyan;
  }
</style>
