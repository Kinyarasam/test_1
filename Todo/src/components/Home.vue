<template>
    <div class="bg-black text-[#d4d4d4] h-screen">
        Home View
        <div class="mx-8 my-4 p-4 flex justify-center bg-[#2a2a2a] rounded shadow-lg shadow-[#6a6a6a]">
            <div>
                <div>
                    <AddTask @add_task="Add_Task" />
                </div>
                <div>
                    <ShowTasks :tasks="tasks"/>
                </div>
            </div>
        </div>
    </div>    
</template>

<script>
import AddTask from './AddTask.vue'
import ShowTasks from './ShowTask.vue'

export default {
    name: 'Home',
    components: {
        AddTask
    },
    data() {
        return {}
    },
    methods: {
        async addTask () {
            const res = await fetch('api/tasks', {
                method: 'POST',
                header: {
                    'Content-type': 'application/json',
                },
                body: JSON.stringify(task)
            })
            const data = await res.json()

            this.tasks = [...this.tasks, data]
        }
    }
}
</script>