<template>
    <form @submit="HandleSubmit">
        <input type="text" placeholder="Task" v-model="task" required />
        <input type="text" placeholder="Category" v-model="category" required />
        <input type="submit" value="Add" class="btn btn-primary" />
    </form>
</template>

<script>
export default {
    name: "Form",
    props: ["index"],
    methods: {
        HandleSubmit(e) {
            e.preventDefault();
            const new_task = {
                id: this.index + 1,
                task: this.task,
                category: this.category,
                timestamp: new Date()
            }
            this.$emit("AddTaskEvent", new_task);
        },
    },
    data() {
        return {
            task: "",
            category: ""
        }
    }
}
</script>

<style>

</style>