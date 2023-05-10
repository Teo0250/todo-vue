<script setup>
    const props = defineProps(['tarefas', 'renderiza']);
</script>

<template>
    <ul class="list-group mt-4" v-if="!props.renderiza">
        <li class="list-group-item" v-for="tarefa in props.tarefas">
            <input @change="evento => tarefa.finalizada = evento.target.checked" :checked="tarefa.finalizada" :id="tarefa.titulo" type="checkbox">
            <label :class="{ done: tarefa.finalizada }" class="ms-3" :for="tarefa.titulo">
                {{ tarefa.titulo }}
            </label>
        </li>
    </ul>
    <h4 v-else class="mt-4">Não existem tarefas disponiveis</h4>
</template> 