<template>
    <div>
        <h3>Add Todo</h3>
        <div class="add form-group text-center">
            <form @submit="onSubmit">
                <input
                    class="form-control"
                    type="text"
                    v-model="title"
                    placeholder="Add todo"
                />
                <input class="btn btn-primary" type="submit" value="Submit" />
            </form>
        </div>
    </div>
</template>

<script>
import { mapActions } from 'vuex';
export default {
    name: 'AddTodo',
    data() {
        return { title: '' };
    },
    methods: {
        ...mapActions(['addTodo']),
        onSubmit(e) {
            e.preventDefault();
            this.addTodo(this.title);
        }
    }
};
</script>

<style scoped></style>
