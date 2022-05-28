<template>
  <q-page class="q-pa-md">
		
		<no-tasks
			v-if="!Object.keys(tasksTodo).length"></no-tasks>

		<tasks-todo
			v-else
			:tasksTodo="tasksTodo" />

  </q-page>
</template>

<script>
	import { mapGetters } from 'vuex'

	export default {
		computed: {
			...mapGetters('tasks', ['tasksTodo', 'tasksCompleted'])
		},
		components: {
			'tasks-todo' : require('components/Tasks/TasksTodo.vue').default,
			'no-tasks' : require('components/Tasks/NoTasks.vue').default
		}
	}
</script>

<style>
	
</style>
