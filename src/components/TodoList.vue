<script setup>
	import { useTodoListStore } from "../stores/todoList"
	import { storeToRefs } from "pinia"

	const store = useTodoListStore()
	const { toggleCompleted, deleteTodo } = store
	const { todoList } = storeToRefs(store)
</script>

<template>
	<div
		@click="console.log('click padre')"
		v-for="todo in todoList"
		:key="todo.id">
		<span :class="{ 'todoList__item--completed': todo.completed }">
			{{ todo.item }}
		</span>
		<div>
			<span
				class="todoList__icon"
				@click.stop="toggleCompleted(todo.id)">
				&#10004;</span
			>
			<span
				class="todoList__icon"
				@click.stop="deleteTodo(todo.id)">
				&#10060;</span
			>
		</div>
	</div>
</template>

<style lang="scss" scoped>
	div {
		display: flex;
		justify-content: space-between;
		font-size: 1.5rem;
		padding: 5px;
	}

	span {
		margin: 0 10px;
		cursor: pointer;
	}

	.todoList {
		&__item {
			&--completed {
				color: red;
				text-decoration: line-through;
			}
		}

		&__icon {
			cursor: pointer;
			user-select: none;
		}
	}
</style>
