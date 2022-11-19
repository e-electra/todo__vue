<template >
    <div class="form" v-if="activeStatus">
        <label class="form__label task-row">
            <p class="task-row__title">Title</p>
            <input type="text" class="task-row__input" v-model="task.titleValue" v-on:keypress.enter="addTask"
                maxlength="30">
        </label>
        <label class="form__label task-row">
            <p class="task-row__title">Description</p>
            <input type="text" class="task-row__input" v-model="task.descValue" v-on:keypress.enter="addTask"
                maxlength="50">
        </label>
        <button class="form__button btn" @click="addTask">Add</button>
        <div class="form__close close-btn" @click="hidePopup">
            <button class="close-btn__wrap cl-btn">
            </button>
        </div>
    </div>
</template>
<script>

// import "./styles/taskInput/";

export default {
    props: {
        activeStatus: {
            type: Boolean,
        },
    },

    data() {
        return {
            task: {
                titleValue: '',
                descValue: ''
            },
        };
    },

    methods: {
        hidePopup: function (props) {
            this.$emit('update:activeStatus', false)
        },

        addTask() {
            if (this.task.titleValue === '') { return };
            this.task.id = Date.now();
            this.$emit('createPost', this.task)
            this.task = {
                titleValue: '',
                descValue: ''
            }
        }
    },
}
</script>

<style lang="scss">
// @import "./styles/taskInput/task-input";
</style>