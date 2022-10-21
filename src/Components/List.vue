<template>
    <section v-for="t in tasklist_prop">
        <h4><i>{{t.id}}</i> - {{t.task}}</h4>
        <h5>{{t.timestamp}}</h5>
        <Delete></Delete>
    </section>
</template>

<script>
import Delete from "./Delete.vue";

export default {
    name: "List",
    props: {
        tasklist_prop: Array
    },
    data() {
        return {
            list: this.tasklist_prop
        };
    },
    components: { Delete }
}
</script>

<style>

</style>