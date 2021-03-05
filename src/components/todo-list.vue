<template>
<div class="tdl" v-for="(task,index) in tasks" v-bind:key="index"> 
    <input type="checkbox" id="checkbox" @click="checkTask(index)">
    <p>{{task.name}}</p>
    <button class="supr"> 
            X
    </button>
</div>
</template>

<script>
export default {
    props: {
        tasks: {
            type : Array
        }
    },
        methods: {
        checkTask(index){
                this.$emit('check', index)
                
    }
    },
}
</script>

<style>

</style>