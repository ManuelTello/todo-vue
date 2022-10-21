<template>
    <form @submit="HandleSubmit">
        <input type="text" placeholder="Something" v-model="task" />
        <input type="submit" value="Add" />
    </form>
</template>

<script>
import Delete from "./Delete.vue";

export default {
    name: "Form",
    props: {
        index: Number
    },
    methods: {
        HandleSubmit(e) {
            e.preventDefault();
            const new_task = {
                id: this.index + 1,
                task: this.task,
                timestamp: new Date()
            }
            this.$emit("AddTaskEvent", new_task);
        },
    },
    data() {
        return {
            task: ""
        }
    }
}
</script>

<style>

</style>