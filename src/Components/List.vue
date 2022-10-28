<template>
    <form @submit="HandleFilter">
    </form>
    <section v-for="t in tasklist_prop">
        <h4><i>{{ t.id }}</i> - {{ t.task }}</h4>
        <h3>Category: {{ t.category }}</h3>
        <h5>{{ t.timestamp }}</h5>
        <button @click="HandleDelete(t.id)" class="btn btn-danger">Delete</button>
    </section>
</template>

<script>
export default {
    name: "List",
    components: {},
    emits: {
        click: null,
        EventDeleteTask: ({ id }) => true
    },
    props: ["tasklist_prop"],
    data() {
        return {
            list: this.tasklist_prop
        };
    },
    methods: {
        HandleDelete(id) {
            this.$emit("EventDeleteTask", id);
        },
        HandleFilter(e) {
            e.preventDefault();
        }
    }
}
</script>

<style>

</style>