<template>
    <form @submit.prevent="getWeather">
        <input class="input" type="text" placeholder="City name here" v-model="city">
        <button class="submit">Submit</button>
    </form>
</template>

<script>
export default {
    name: 'Input',
    data () {
        return {
        title: 'Vue Weather App',
        city: '',
        }
    },
    methods: {
        async getWeather() {
            try {
                this.showLoading = true;
                const response = await fetch(
                `https://api.openweathermap.org/data/2.5/weather?q=${this.city}&units=metric&appid=ce7201d8348f6361c51c87e0ea6496d4`
                );
                const weatherData = await response.json();
                this.$emit('data', weatherData)
            } catch (err) {
                console.log(err);
            } finally {
                this.showLoading = false;
            } 
        }
    },
}
</script>

<style scoped>
    .input {
        background-color: rgb(116, 226, 208);
        border: none;
        padding: 10px 20px;
        margin-bottom: 20px;
        border-radius: 5px;
        outline: none;
        font-family: "Montserrat", sans-serif;
        margin-right: 5px;
    }

    .input::placeholder {
        font-family: 'Montserrat', sans-serif;
        color: black;
    }

    .submit {
        background-color: lightseagreen;
        border: none;
        padding: 10px 20px;
        margin-bottom: 20px;
        border-radius: 5px;
        font-family: "Montserrat", sans-serif;
        outline: none;
    }

    .submit:hover {
        background-color: darkcyan;
        transition: 0.4s;
        cursor: pointer;
    }
</style>