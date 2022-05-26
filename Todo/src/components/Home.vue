<template>
    <div class="bg-black text-[#d4d4d4] h-screen">
        Home View
        <div class="mx-8 my-4 p-4 flex justify-center bg-[#2a2a2a] rounded shadow-lg shadow-[#6a6a6a]">
            <div>
                <div>
                    <AddTask />
                </div>
                <div>
                    SHOW TASKS
                </div>
            </div>
        </div>
    </div>    
</template>

<script>
import AddTask from './AddTask.vue'

export default {
    name: 'Home',
    components: {
        AddTask
    }
}
</script>