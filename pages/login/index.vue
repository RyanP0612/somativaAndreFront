<script setup>
    definePageMeta({
        layout: "loginlay"
    });
    // função useFetch vai chamar o backend como se fosse no Insomnia
    const { data: allLogin } = await useFetch('http://localhost:8000/usuarios',{
      key: 'usuarioRequest' 
    });

</script>


<template>
    <div>
        <h1>
            bem vindo ao login
        </h1>
        <h3 >Insira suas informações abaixo!!</h3>
        <label for="">Email: </label>
        <select v-model="emails">
        <option value=""></option>

        <option v-for="usuarios in allLogin.data" :key="usuarios.id">
            
           {{ usuarios.nome }}
            <!-- <img :src="'http://localhost:8000' + filme.foto" alt="foto filme"> -->
            <!-- <NuxtLink :to="'/trips/' + image.tripFk"></NuxtLink> -->

        </option>
        </select>
        <br>
        <br>
        <NuxtLink to="/">
        <button v-if="emails  !== ''" @click="realizarAcao ">Login</button>
        </NuxtLink>
        <br>


    </div>
</template>


<script>
export default {
  data() {
    return {
      emails: '' // Inicializa a variável para armazenar a opção selecionada
    };
  }
};
</script>



