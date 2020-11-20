<template>
  <div id="app" @data="getWeatherData">
    <h1>{{title}}</h1>
    <Form />
    <Card />
  </div>
</template>

<script>
import Card from './components/Card'
import Form from './components/Form'

export default {
  name: 'App',
  components: {
    Card,
    Form,
  },
  data() {
    return {
      title: 'Vue Weather App',
      temperature: '',
      icon: '',
      showCard: false,
      loading: false,
    }
  },
  methods: {
    getWeatherData() {
      console.log("app data", this.weatherData)
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

  .input-container{
    display: flex;
    margin-top: 20px;
  }
</style>
