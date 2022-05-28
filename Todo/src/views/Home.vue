<template>
    <div class="bg-black text-[#d4d4d4] h-screen pt-2">
        
        <div class="mx-8 my-4 p-4 flex justify-center bg-[#2a2a2a] rounded shadow-lg shadow-[#6a6a6a]">
            <div class="">
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
import AddTask from '../components/AddTask.vue'
import ShowTasks from '../components/ShowTask.vue'

export default {
    name: 'Home',
    components: {
        AddTask,
        ShowTasks
    },
    data() {
        return {
            tasks: [],
        }
    },
    methods: {
        async Add_Task () {
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