<template>
  <div class="task-grid">
    <template v-if="tasks.length">
        <TaskItem v-for="(task, i) in tasks" :key="i" :task="task" @taskDeleted="$emit('taskDeleted', i)" @taskStateChanged="$emit('taskStateChanged', i)"/>
    </template>
    <p v-else class="no-task">Sua vida está em dia :D</p>
  </div>
</template>

<script>
import TaskItem from './TaskItem.vue';
export default {
    name: 'task-grid',
    components: {
        TaskItem
        },
    props: {
        tasks: {
            type: Array,
            require: true
        }
    }
}
</script>

<style>
    .task-grid {
        display: flex;
        justify-content: center;
        flex-wrap: wrap;
        /*flex-direction: column;*/
        /* gap: 20px; */
    }

    .task {
        margin: 10px;
    }
    no-task {
        font-size: 1.7rem;
    }
</style>