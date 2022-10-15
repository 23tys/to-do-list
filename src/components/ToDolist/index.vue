<template>
	<div>
		<to-do-header @addTodo="addTodo" />
		<Underway :todolists="todolists" @click="finish"></Underway>
		<Completetd :todolists="finishlists" @click="todo"></Completetd>
	</div>
</template>

<script>
	import ToDoHeader from './Header.vue';
	import Underway from './Underway.vue';
	import Completetd from './Completed.vue';
	export default {
		components: {
			ToDoHeader,
			Underway,
			Completetd
		},
		data(){
			return{
				todolists:[],
				finishlists:[]
			}
		},
		methods:{
			addTodo(obj){
				this.todolists.push(obj);
			},
			finish(item){
				this.finishlists.push(item)
			},
			todo(item){
				this.todolists.push(item)
			}
		}
	}
</script>

<style >
	.todolist-container{
		width: 1000px;
		margin: 0 auto;
	}
</style>
