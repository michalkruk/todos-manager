<template>
    <div>
        <h3>Todos</h3>
        <div class="card-columns">
            <div
                v-for="todo in allTodos"
                :key="todo.id"
                class="card text-white bg-primary p-4 mb-3"
                style="max-width: 20rem;"
            >
                <div class="class-text text-center">
                    {{ todo.title }}
                    <i
                        @click="deleteTodo(todo.id)"
                        class="fas fa-trash-alt"
                    ></i>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import { mapGetters, mapActions } from 'vuex';
export default {
    name: 'Todos',
    methods: {
        ...mapActions(['fetchTodos', 'deleteTodo'])
    },
    computed: mapGetters(['allTodos']),
    created() {
        this.fetchTodos();
    }
};
</script>

<style scoped>
i {
    position: absolute;
    bottom: 10px;
    right: 10px;
    cursor: pointer;
}
</style>
