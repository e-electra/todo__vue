<template>
    <div class="page-body">
        <div class="container">
            <main class="main">
                <TaskNote v-model:activeStatus="isVisible" :create="addTask" v-bind:taskList="taskList"></TaskNote>
            </main>
            <footer class="footer">
                <p class="footer__descr">
                    © 2022. Author Name
                </p>
            </footer>
        </div>
        <div class="popup-bg" v-if="isVisible" @click="hidePopup"></div>
        <TaskInput v-model:activeStatus="isVisible" @createPost="addTask"></TaskInput>
    </div>
</template>

<script>

import "./style.scss";

import TaskNote from './components/TaskNote.vue';
import TaskInput from './components/TaskInput.vue';

export default {
    name: 'App',
    components: {
        TaskNote,
        TaskInput,
    },

    data() {
        return {
            isVisible: false,
            taskList: [
            ],
        };
    },

    methods: {
        addTask(task) {
            this.taskList.push(task);
            this.isVisible = false;
        }
    },
}

</script>

<style lang="scss">

</style>