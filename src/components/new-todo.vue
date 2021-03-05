<template>
<div class="form">
    <form action="">
        <input type="text" placeholder="Nouvelle tâche..." class="imput" v-model="task">
        <button class="bouton" @click='sendTask(task)'> 
            +
        </button>
    </form>
</div>
</template>

<script>
export default {
    data() {
        return {
            task : ""
        }
    },
    methods: {
        sendTask(){
            if(this.task != "") {
                this.$emit('sendTask', this.task )
                console.log(this.task)}
    },
    }
}
</script>

<style>

</style>