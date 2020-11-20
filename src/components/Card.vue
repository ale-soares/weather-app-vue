<template>
    <div class="card">
        <img class="image" src="" alt="temperature icon">
        <p class="temperature">dasuidh</p>
    </div>
</template>

<script>
    export default {
        name: 'Card',
    }
</script>

<style scoped>
    .card {
        background-color: rgb(116, 226, 208);
        padding: 3em;
        width: 320px;
        border: none;
        border-radius: 15px;
    }

    .image {
        width: 200px;
    }

    .temperature {
        font-size: 30px;
        color: lightseagreen;
        font-weight: 700;
        margin: 5px 5px 0;
    }
</style>