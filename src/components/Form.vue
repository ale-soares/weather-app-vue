<template>
    <form class="form" @submit.prevent="fetchData">
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
        fetchData() {
            this.$emit("fetchData", this.city)
        }
    },
    
}
</script>

<style scoped>
    .form {
        margin-top: 20px;
    }
    
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