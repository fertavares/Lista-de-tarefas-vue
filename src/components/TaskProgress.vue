<template>
  <div class="tasks-progress">
    <span class="progress-value">{{ progress }}%</span>
    <div class="progress-bar"></div>
  </div>
</template>

<script>
export default {
    name: 'tasks-progress',
    props: {
        progress: {
            type: Number,
            default: 0
        }
    }
}
</script>

<style scoped>
    .tasks-progress {
        position: relative;
        width: 80%;
        border: 1px solid white;
        color: white;
        border-radius: 8px;
        margin-bottom: 15px;
        display: flex;
        align-items: center;
        flex-direction: center;
    }
    .progress-bar {
        position: absolute;
        border-radius: 8px;
        height: 100%;
        background-color: greenyellow;
        align-self: flex-start;
    }
    .progress-value {
        z-index: 1;
        font-size: 1.5rem;
    }
</style>