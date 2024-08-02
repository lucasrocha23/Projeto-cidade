<script setup>
const {cidade} = defineProps({
    cidade:{
        type: Object,
        required: true
    },
    categoria:{
        type: String,
        required: true
    }
})

</script>

<template>
    <div v-for="local in cidade.locais" >
        <div class="card_local"  v-show="local.categoria == categoria">
            <div class="nome">
                <p>{{ local.nome }}</p>
            </div>
            <div class="dados">
                <img :src="local.img" width="300" height="300">
                <p class="descricao">{{ local.descricao }}</p>
            </div>
        </div>
    </div>
</template>

<style>
.card_local{
  box-shadow: 10px 10px 20px rgba(0, 0, 0, 0.3);
  border-radius: 10px;
  margin-bottom: 50px;
  padding: 20px;
}

.card_local:hover{
  background-color: rgb(219, 219, 219);
}

.card_local .nome{
  border-bottom: solid 1px darkgray;
  padding-bottom: 5px;
  margin-bottom: 5px;
}

.card_local .nome p{
  font-size: 2.3rem;
  font-weight: bold;
  text-align: start;
}

.card_local .dados{
  display: flex;
}

.card_local .dados .descricao{
    flex: 1;
    padding: 20px ;
    display: flex;
    align-items: center;
    text-align: justify;
    font-size: 1.2rem;
}
</style>