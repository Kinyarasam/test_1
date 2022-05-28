<template>
    <div class="border-b-2 pb-3">
        <form @submit.prevent="onSubmit">
            <div>
                <label for="task">Add Task:</label>
                <input 
                    v-model="title"
                    name="Task" 
                    type="text"
                    placeholder="Add New Task"
                    class="block bg-black px-2 rounded-lg py-1.5 focus:border-none"
                />
            </div>
            <div class="mt-2">
                <label for="task">Day & Time</label>
                <input 
                    name="day" 
                    v-model="day"
                    type="text"
                    placeholder="Add Day and Time"
                    class="block bg-black px-2 rounded-lg py-1.5 focus:border-none"
                />
            </div>
            <div class="my-2">
                <label for="task">Add Description:</label>
                <input 
                    name="Task"
                    v-model="description"
                    type="text"
                    placeholder="Add New Task"
                    class="block bg-black px-2 rounded-lg py-1.5 focus:border-none"
                />
            </div>
            <div >
                <label for="task">completed: </label>
                <input 
                    name="completed" 
                    v-model="completed"
                    type="checkbox"
                    class="bg-black px-2 rounded-lg py-1.5 focus:border-none"
                />
            </div>
            <input type="submit" 
                class="bg-teal-500 px-5 py-1.5 rounded text-black font-semibold hover:scale-110"
            />
        </form>
    </div>
</template>

<script>
export default {
    name: 'AddTask',
    data() {
        return {
            title: '',
            day: '',
            description: '',
            completed: false
        }
    },
    methods: {
        onSubmit(data) {
            data.preventDefault()

            if (!this.title) {
                alert('Please add a task')
                console.alert('Invalid Input')
            }
            else if (!this.day) {
                alert('Please add a day')
                console.alert('Invalid Input')
            }
            else if (!this.description) {
                alert('Please add a Description')
                console.alert('Invalid Input')
            }

            const newTask = {
                title: this.title,
                day: this.day,
                description: this.description,
                completed: this.completed
            }

            this.$emit('add_Task', newTask)

            this.task = '',
            this.day = '',
            this.description = ''
            console.log(newTask)
        }
    }
}

</script>

<style>

</style>