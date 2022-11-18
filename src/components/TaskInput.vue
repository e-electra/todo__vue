<template >
    <div class="form">
        <label class="form__label">
            <p>Title</p>
            <input type="text" v-bind:value="valueInput" v-on:input="handlyInput" v-on:keypress.enter="addTask">
        </label>
        <label class="form__label">
            <p>Description</p>
            <textarea name="" id="" cols="10" rows="3"></textarea>
        </label>
        <button class="btn" v-on:click="addTask">Add</button>
    </div>
</template>
<script>
export default {



}

</script>
<style >

</style>