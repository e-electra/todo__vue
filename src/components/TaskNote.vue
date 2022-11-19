<template >
    <div class="planner">
        <div class="planner__wrap">
            <div class="planner__header planner-header">
                <h2 class="planner-header__title">Todo List</h2>
                <button class="planner-header__link btn" @click="showPopup">Add</button>
            </div>
            <ul class="planner__tasks tasks">
                <li class="tasks__item task-item" v-for="task in taskList" :key="task.id">
                    <label class="task-item__label">
                        <input type="checkbox" class="task-item__checkbox">
                        <div class="task-item__descr">
                            <h3 class="task-item__title">{{ task.titleValue }}</h3>
                            <p class="task-item__text">{{ task.descValue }}</p>
                        </div>
                    </label>
                </li>
            </ul>
        </div>
    </div>
</template>

<script>

export default {
    props: {
        taskList: {
            type: Array,
            required: true
        }
    },

    methods: {
        showPopup: function (props) {
            this.$emit('update:activeStatus', true)
        },
    },
}
</script>

<style lang="scss">
// @import "./styles/taskNote/task-note";
</style>