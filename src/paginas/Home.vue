<script setup>
const {cidade} = defineProps({
    cidade:{
        type: Object,
        required: true
    }
})
</script>

<template>
    <section>
        <h1>{{cidade.nome}}</h1>
        <div class="img"><img :src="cidade.img" width="700" height="400"></div>
        <p>{{ cidade.sobre }}</p>
    </section>
</template>

<style>
section{
    font-size: 1.3rem;
}

section h1{
    font-weight: bold;
    margin-top: 20px;
}

.img {
    margin: 50px 0;
    display: flex;
    justify-content: center;
}

section p{
    text-align: justify;
    text-indent: 1.5rem;
    box-shadow: 10px 10px 20px rgba(0, 0, 0, 0.3);
    border-radius: 10px;
    /* margin-bottom: 50px; */
    padding: 20px;
}
</style>