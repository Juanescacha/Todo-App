<script setup>
	import { ref } from "vue"
	import { useTodoListStore } from "@/stores/todoList"

	const todo = ref("")
	const store = useTodoListStore()

	const addItemAndClear = item => {
		if (item.length > 0) {
			store.addTodo(item)
			todo.value = ""
		}
	}
</script>

<template>
	<form @submit.prevent="addItemAndClear(todo)">
		<input
			type="text"
			v-model="todo" />
		<button>Add</button>
	</form>
</template>

<style lang="scss" scoped>
	form {
		margin-bottom: 15px;
	}
	input {
		margin-top: 25px;
		margin-bottom: 15px;
		height: 20px;
		width: 50%;
	}
	button {
		margin-left: 30px;
		background-color: #2f6089;
		padding: 5px 10px;
		border: none;
		border-radius: 5px;
		font-weight: 800;
		color: white;
		width: 15%;
	}
	.alert-div {
		min-height: 25px;
	}
	.alert {
		color: #d1495b;
		font-size: 1em;
		font-weight: 600;
	}
</style>
