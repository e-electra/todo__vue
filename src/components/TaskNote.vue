<template >
    <div class="planner">
        <div class="planner__wrap">
            <div class="planner__title title">
                <h2 class="title__logo">Todo List</h2>
                <a href="#" class="title__link btn">Add</a>
            </div>
            <div class="title__tasks tasks">
                <ul class="tasks__list">
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
                    <li class="tasks__item to-do">
                        <label class="to-do__item">
                            <input type="checkbox" class="to-do__check">
                            <div class="to-do__descr">
                                <h3 class="to-do__title">repellendus sunt dolores architecto voluptatum</h3>
                                <p class="to-do__text">accusamus eos facilis sint et aut voluptatem</p>
                            </div>
                        </label>
                    </li>
                    <li class="tasks__item to-do" v-for="(mask, index) in needDoList" :key="mask.id">
                        <label class="to-do__item">
                            <input type="checkbox" class="to-do__check">
                            <div class="to-do__descr">
                                <h3 class="to-do__title">{{ mask.title }}</h3>
                                <p class="to-do__text">accusamus eos facilis sint et aut voluptatem</p>
                            </div>
                        </label>
                    </li>

                </ul>
            </div>
        </div>
    </div>
</template>

<script>
export default {

    setup(props) {

    }

}
</script>

<style>

</style>