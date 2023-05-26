<script setup>
// import HelloWorld from './components/HelloWorld.vue'
// import TheWelcome from './components/TheWelcome.vue'
import { ref } from 'vue'

//const saludo = 'Hola mundo'
//const complemento = ref('cruel') complemento no es constante de js, porque tiene ref es una especie de objeto de Vue
//complemento.value = 'Bonito'


const solicitudes = ref(0)
const incrementar = () =>{
  solicitudes.value ++
}
const decrementar = () =>{
  if(solicitudes.value > 0){
    solicitudes.value--
  }
}

const tittle = ref("Mega ejemplo")
</script>

<template>
  <h2>{{ tittle }}</h2>
  <div class="user">
    <svg
      xmlns="http://www.w3.org/2000/svg"
      fill="none"
      viewBox="0 0 24 24"
      stroke-width="1.5"
      stroke="currentColor"
      class="w-6 h-6"
    >
      <path
        stroke-linecap="round"
        stroke-linejoin="round"
        d="M17.982 18.725A7.488 7.488 0 0012 15.75a7.488 7.488 0 00-5.982 2.975m11.963 0a9 9 0 10-11.963 0m11.963 0A8.966 8.966 0 0112 21a8.966 8.966 0 01-5.982-2.275M15 9.75a3 3 0 11-6 0 3 3 0 016 0z"
      />
    </svg>
    <div v-if="solicitudes > 0" class="notification">
      {{ solicitudes }}
    </div>
  </div>
  <br>
  <span @click=incrementar> + </span>
  <span @click="decrementar"> - </span>

  <div v-show="solicitudes > 0 ">Wooho !! Tengo solicitudes</div>
  <input type="text" v-model="tittle">
</template>

<style scoped>
span{
  background:gold;
  display: inline-block;
  border-radius: 4px;
  text-align: center;
  margin: 10px;
  width: 30px;
  height: 30px;

}
span:hover{
  color:red;
  background-color: burlywood;
  cursor: pointer;
}
.user {
  position: relative;
  width: 70px;
  height: 70px;
}

.notification {
  position: absolute;
  top: -10px;
  right: -10px;
  background-color: red;
  border-radius: 50%;
  width: 30px;
  height: 30px;
  color: white;
  text-align: center;
}
</style>
