<template>
    <div class="page-body">
        <div class="container">

            <main class="main">
                <div class="planner">
                    <div class="planner__wrap">
                        <div class="planner__title title">
                            <h2 class="title__logo">Todo List</h2>
                            <a href="#" class="title__link btn" @click="() => TogglePopup('buttonTrigger')">Add</a>
                        </div>
                        <ul class="title__tasks tasks">

                            <li class="tasks__item to-do">
                                <label class="to-do__item">
                                    <input type="checkbox" class="to-do__check">
                                    <div class="to-do__descr">
                                        <h3 class="to-do__title">delectus aut autem </h3>
                                        <p class="to-do__text">laboriosam mollitia et enim quasi adipisci quia
                                            provident
                                            illum</p>
                                    </div>
                                </label>
                            </li>
                            <li class="tasks__item to-do">
                                <label class="to-do__item">
                                    <input type="checkbox" class="to-do__check">
                                    <div class="to-do__descr">
                                        <h3 class="to-do__title">quo laboriosam deleniti aut qui</h3>
                                    </div>
                                </label>
                            </li>
                            <li class="tasks__item to-do">
                                <label class="to-do__item">
                                    <input type="checkbox" class="to-do__check">
                                    <div class="to-do__descr">
                                        <h3 class="to-do__title">laboriosam mollitia et enim quasi adipisci quia
                                            provident illum</h3>
                                    </div>
                                </label>
                            </li>



                            <li class="tasks__item to-do" v-for="(task, index) in needDoList" :key="task.id">
                                <label class="to-do__item">
                                    <input type="checkbox" class="to-do__check">
                                    <div class="to-do__descr">
                                        <h3 class="to-do__title">{{ task.title }}</h3>
                                        <p class="to-do__text">{{ task.desc }}</p>
                                    </div>
                                </label>
                            </li>


                        </ul>
                    </div>
                </div>
            </main>

            <footer class="footer">
                <p class="footer__descr">
                    © 2022. Author Name
                </p>
            </footer>



        </div>

        <div class="popup-bg" v-if="popupTriggers.buttonTrigger"></div>

        <div class="form" v-if="popupTriggers.buttonTrigger">
            <label class="form__label task-row">
                <p class="task-row__title">Title</p>
                <input type="text" class="task-row__input" v-bind:value="titleValue" v-on:input="SetTitle"
                    v-on:keypress.enter="addTask" maxlength="30">
            </label>
            <label class="form__label task-row">
                <p class="task-row__title">Description</p>
                <input class="task-row__input" v-bind:value="descValue" v-on:input="SetDesc"
                    v-on:keypress.enter="addTask" maxlength="50">
            </label>
            <button class="form__button btn" v-on:click="addTask">Add</button>
            <div class="form__close close-btn" @click="() => TogglePopup('buttonTrigger')">
                <button class="close-btn__wrap cl-btn">
                </button>
            </div>
            <!-- <button class="btn" @click="() => TogglePopup('buttonTrigger')">Close</button> -->
        </div>
    </div>



</template>
<script>

import TaskNote from './components/TaskNote.vue';
import TaskInput from './components/TaskInput.vue';
import { ref } from 'vue';

export default {
    name: 'App',
    components: {
        TaskNote,
        TaskInput
    },

    setup() {
        const popupTriggers = ref({
            buttonTrigger: false,
        });

        const TogglePopup = (trigger) => {
            popupTriggers.value[trigger] = !popupTriggers.value[trigger]
        }

        return {
            popupTriggers,
            TogglePopup
        }
    },


    data() {
        return {
            titleValue: '',
            descValue: '',
            needDoList: []
        };
    },

    methods: {
        SetTitle(event) {
            this.titleValue = event.target.value;

        },
        SetDesc(event) {
            this.descValue = event.target.value;

        },
        addTask() {
            if (this.titleValue === '') { return };
            this.needDoList.push({
                title: this.titleValue,
                desc: this.descValue,
                id: Math.random()
            });
            this.titleValue = '';
            this.descValue = '';
            this.TogglePopup('buttonTrigger');
        }
    }

}



</script>


<style>
@import "css/style.css"
</style>