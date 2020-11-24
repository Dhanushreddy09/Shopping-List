<template>
<div>
    <div id="add">
    <input type="text" v-model="newitem" placeholder="Enter a Todo" v-bind:class="{'form-control form-control-lg':!showerror,'form-control form-control-lg is-invalid':showerror}">
    <button @click="add(newitem)" class="btn btn-lg bg-success text-white">ADD</button>
    </div>
    <div v-if="showerror" class="text-danger ml-5">{{error}}</div>
    <br/>
    <div class="card mt-3" v-for="todo in todolist" :key='todo.id'>
         <div class="card-title mt-3"><h5> {{todo.todo}}</h5></div>
         <i @click="deletetodo(todo.id)" class="fa fa-trash ml-auto mt-0" ></i>
    </div>
    <h4 v-if="todolist.length==0" class="text-secondary">Zero items in your shopping list</h4>
    </div>
</template>
<script>
export default {
    data:function(){
        return{
        newitem:'',
        showerror:false,
        error:'',
        todolist:[
            {todo:"Lentils",id:1},
            {todo:"Burger",id:2},
            {todo:"Tooth Brush",id:3}]
    }
    },
    methods:{
        deletetodo:function(id){
           this.todolist=this.todolist.filter(todo=>todo.id!==id);

        },
        add:function(item,e){
             if(item==''){
                 this.showerror=true;
                 this.error='Please enter a valid todo'
             }
             else{
            this.showerror=false
             this.newitem=''
             var length=this.todolist.length+1
             const newitem={
                 todo:item,
                 id:length++
             }
             this.todolist=[newitem,...this.todolist]
             }
        }
    }
}
</script>
<style scoped>
input{
    width:60%;
    margin:auto;
}
button{
    position:absolute;
    left:82%;
    top:9%
}
.card{
    width: 60%;
    margin:auto
}
.card-title{
    margin-left: 15px;
}
i{
    font-size: 20px;
    position: absolute;;
    top:30%;
    right: 5%;
    cursor: pointer;
}
.text-danger{
    position: relative;
    left: 17%;
}
h4{
    position: relative;
    left:20%
}
</style>