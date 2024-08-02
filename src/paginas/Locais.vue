<script setup>
import {ref} from 'vue'
import CardLocal from '@/components/CardLocal.vue';

const {cidade} = defineProps({
    cidade:{
        type: Object,
        required: true
    }
})

const categoria = ref('')
</script>

<template>
    <div class="select">
        <label>Categoria </label>
        <select v-model="categoria" >
            <option>Restaurante</option>
            <option>Ponto turístico</option>
            <option>Museu</option>
        </select>
    </div>

    <CardLocal :categoria="categoria" :cidade="cidade" v-if="categoria"/>
    <p v-else>Para ver as informações por favor selecione uma categoria!</p>
    
</template>

<style scoped>


.select{
    margin: 20px 0 50px 0;
    font-size: 1.5rem;
}

.select select{
    border-radius: 5px;
    font-size: 1.4rem;
}

p {
    font-size: 1.5rem;
    text-align: center;
    margin-top: 100px;
}
</style>