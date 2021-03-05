<template>
<div class="todo">
    <div class="header">
        <p>{{date}}</p>
        <p class="blue"><b>{{titre}}</b></p>
        <p>{{tasks.length}}  taches</p>
    </div>
    <div class="zonentre">
        <new-todo @sendTask="AddTask"></new-todo>
        <todo-list v-bind:tasks="tasks" @remover="removeTask"></todo-list>
    </div>
</div>
</template>

<script>
import newTodo from './new-todo.vue';
import TodoList from './todo-list.vue';
    export default {
  components: { newTodo, TodoList },
        data(){
            return {
            titre:"VueJs Tutorial ToDo List",
            tasks:[

            ],
            day:["Lundi","Mardi","Mecredi","Jeudi","Vendredi","Samedi","Dimanche"],


        }
        },
        computed: {
            date: function(){
                let todayDate = new Date();

                console.log(todayDate)
                return `${todayDate.getDay()} / ${todayDate.getMonth()+1} / ${todayDate.getFullYear()}`

            }
        },
        methods: {
            AddTask(task){
                let newTask = { name: task, statut: false };
                this.tasks.push(newTask)
            },
            removeTask(index){
                this.tasks.splice(index,1);
            }
        },
    }
</script>

<style>
.todo{
    background-color: white;
    border-radius: 20px;
   
}
.header{
     display: flex;
    justify-content: space-around;
}
.blue{
    color: lightseagreen;
}
.zonentre{
    background-color:antiquewhite;
}
.imput{
    border: none;
    background-color:antiquewhite;
    color: black 0.5;
    text-align: center;
    font-size: 20px;
    border-bottom: aqua solid 3px;
}
.bouton{
    background-color: lightseagreen;
    border-radius: 70px;
    border: none;
    color: white;
}
.form{
    display: flex;
    flex-direction: row;
    justify-content: space-around;
}
.supr{
    background-color: red;
    border-radius: 90px;
    border: none;
    color: white;
}
.tdl{
    display: flex;
    justify-content: space-around ;
}
</style>