<template>
    <div>
        <h3>
            {{ task.title  }}
        </h3>
    </div>
</template>

<script>
export default {
    name: 'Task',
    props: {
        task: Object
    }
}
</script>
