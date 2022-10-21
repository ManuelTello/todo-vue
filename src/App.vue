<template>
    <Form :index="todo_list.length" @AddTaskEvent="EventAddTask"></Form>
    <List :tasklist_prop="todo_list"></List>
</template>

<script>
import Form from "./Components/Form.vue";
import List from "./Components/List.vue";

export default {
    name: "App",
    components: { Form, List },
    data() {
        return {
            todo_list: []
        }
    },
    methods: {
        EventAddTask(e) {
            this.todo_list.push(e);
        },
    }
}
</script>

<style>

</style>