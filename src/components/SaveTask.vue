<template>
    <div>
        <label for="add-task-input">
            <div>
                <span>
                    Task
                </span>
                <input type="text" placeholder="What do you need to do?" v-model="newTask.title">
            </div>
            <div>
                <button class="btn btn-primary" type="button" @click="saveTask">Save Item</button>
            </div>
        </label>
    </div>
</template>

<script>
export default {
    data() {
        return {
            newTask: {
                title: ''
            }
        }
    },
    methods: {
        saveTask () {
            this.$emit('created', this.newTask);
            this.newTask = {
                title: ''
            };
        }
    },
}
</script>

<style >
    .btn-primary {
        color: #fff;
        background-color: #007bff;
        border-color: #007bff;
    }
    input {
        color: #495057;
        background-color: #fff;
        background-clip: padding-box;
        border: 1px solid #ced4da;
        border-radius: .25rem;
        border-style: solid;
        padding: 2px;
        line-height: 1.5;
        width: 60%;
        float: right;
    }
</style>