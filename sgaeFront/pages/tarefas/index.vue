<script setup>
// função useFetch vai chamar o backend como se fosse no Insomnia
    const { data: alltarefas } = await useFetch('http://localhost:8000/tarefas?all',{
      key: 'tarefaRequest' 
    });
    
    
    
</script>



<template>
    <div>
        <h1>Bem vindo aos nossos tarefas</h1>
        <section v-for="tarefa in alltarefas.data" :key="tarefa.id">
            
            <h3>Nome: {{ tarefa.nome }}</h3>
            <h3>Status: {{ tarefa.idStatusFK.nome }}</h3>
            <h3>Ambiente: {{ tarefa.idAmbienteFK.nome }}</h3>
            <h3>Prazo: {{ tarefa.prazo }}</h3>
            <NuxtLink :to="`/tarefas/${tarefa.id}`">
                <button>Ir à tarefa</button>
            </NuxtLink>
            <br>
            <hr>
            <br>

            
            <!-- <img :src="'http://localhost:8000' + tarefa.foto" alt="foto tarefa"> -->
            <!-- <NuxtLink :to="'/trips/' + image.tripFk"></NuxtLink> -->

            <!-- <NuxtLink :to="`/tarefas/${tarefa.id}`">
                <img :src="'http://localhost:8000' + tarefa.foto" alt="foto tarefa">
            </NuxtLink> -->
        </section>
        <br><hr>
    </div>
</template>

        
