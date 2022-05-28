<template>
    <div>
        <div v-for="task in tasks" :key="task.id">
            <Task :task="task"/>
        </div>
    </div>
</template>

<script>
import Task from './Task.vue'

export default {
    name: 'ShowTasks',
    props: {
        tasks: Array
    },
    components: {
        Task,
    }

}
</script>

<style>

</style>