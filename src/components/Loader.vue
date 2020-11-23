<template>
    <div>
        <img
        class="loader"
        src="https://www.flaticon.com/svg/static/icons/svg/248/248958.svg"
        alt="loading"
        /> 
    </div>
</template>

<script>
    export default {
        name: 'Loader'
    }
</script>

<style scoped>
    @keyframes rotate {
        from {
            transform: rotate(0deg)
        }
        to {
            transform: rotate(360deg)
        }
    }

    .loader {
        width: 30px;
        animation: rotate 1.5s linear infinite;
    }
</style>