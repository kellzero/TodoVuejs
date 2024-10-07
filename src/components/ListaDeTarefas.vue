<template>
    <div>
        <ul v-if="tarefas.length > 0" class="list-group mt-4">
            <li class="list-group-item" v-for="tarefa in tarefas" :key="tarefa.titulo">
                <input v-model="tarefa.finalizada" :id="tarefa.titulo" type="checkbox">
                <label :class="{ done: tarefa.finalizada }" class="ms-3" :for="tarefa.titulo">
                    {{ tarefa.titulo }}
                </label>
            </li>
        </ul>
        <p v-else>Nenhuma tarefa disponível</p> <!-- Mensagem quando não houver tarefas -->
    </div>
</template>

<script setup>
defineProps(['tarefas']);
</script>

<style scoped>
.done {
    text-decoration: line-through;
}
</style>