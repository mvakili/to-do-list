<template>
    <div>
        <ul>
            <li v-for="(task, index) in tasks" v-bind:key="task">
                <span>{{task.title}}</span>
                <button class="btn btn-danger" type="button" @click="remove(index)">X</button>
                <button class="btn btn-success" type="button" @click="done(index)">✓</button>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
    props: {
        tasks: Array
    },
    methods: {
        done (index) {
            this.$emit('done', index);
        },
        remove (index) {
            this.$emit('remove', index);
        }
    }
}
</script>

<style >
    ul {
        list-style: none
    }
    li {
        background-color: #fafafa;
        padding:10px;
        border-radius: 5px;
        border: 1px solid #ccc!important;
    }
    .btn-success {
        color: #fff;
        background-color: #28a745;
        border-color: #28a745;
    }
    .btn-danger {
        color: #fff;
    background-color: #dc3545;
    border-color: #dc3545;
    }
</style>