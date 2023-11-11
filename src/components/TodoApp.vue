<script setup>
	import TodoForm from "./TodoForm.vue"
	import TodoList from "./TodoList.vue"
</script>

<template>
	<main class="todo-app">
		<h1>To Do List</h1>
		<TodoForm />
		<TodoList />
	</main>
</template>

<style lang="scss" scoped>
	.todo-app {
		padding: 5vh;
		min-height: 100vh;
		width: 30vw;
		background-color: #f7f9fc;
	}
</style>
