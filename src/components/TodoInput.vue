<template>
    <div class="inputBox shadow">
        <input type="text" v-model="newTodoItem" v-on:keyup.enter="addTodo">
        <button v-on:click="addTodo">add</button>
    </div>
</template>
<script>
export default {
    data: function() {
        return{
            newTodoItem: ""
        }
    },
    methods:{
        addTodo: function(){
            console.log(this.newTodoItem);
            localStorage.setItem(this.newTodoItem,this.newTodoItem);
            this.clearInput();
        },
        clearInput: function(){
            this.newTodoItem = "";
        }
    }
}
</script>
<style scoped>
input:focus{
    outline: none;
}
.inputBox{
    background: white;
    
}
</style>