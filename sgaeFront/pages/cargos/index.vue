<script setup>
// função useFetch vai chamar o backend como se fosse no Insomnia
    const { data: allcargos } = await useFetch('http://localhost:8000/cargos',{
      key: 'cargosRequest' 
    });
    
    
    
</script>



<template>
    <div>
        <h1>Bem vindo aos nossos cargos</h1>
        <section v-for="cargo in allcargos.data" :key="cargo.id">
            
            <h3>Cargo: {{ cargo.nome }}</h3>
            <h3>Nível de acesso: {{ cargo.nivelAcesso }}</h3>
            
            <br>
            <hr>
            <br>

            
            <!-- <img :src="'http://localhost:8000' + tarefa.foto" alt="foto tarefa"> -->
            <!-- <NuxtLink :to="'/trips/' + image.tripFk"></NuxtLink> -->

            <!-- <NuxtLink :to="`/cargos/${tarefa.id}`">
                <img :src="'http://localhost:8000' + tarefa.foto" alt="foto tarefa">
            </NuxtLink> -->
        </section>
        <br><hr>
    </div>
</template>

        
