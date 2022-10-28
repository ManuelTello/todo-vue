<template>
    <Form :index="todo_list.length" @AddTaskEvent="EventAddTask"></Form>
    <List :tasklist_prop="todo_list" @EventDeleteTask="EventRemoveTask"></List>
</template>

<script>
import Form from "./Components/Form.vue";
import List from "./Components/List.vue";
import 'bootstrap/dist/css/bootstrap.css'


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
        EventRemoveTask(id) {
            this.todo_list = this.todo_list.filter((e) => e.id !== id);
        }
    }
}
</script>

<style>

</style>