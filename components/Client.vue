<script setup>
defineProps({
	client: {
		type: Object,
		required: true,
	},
})
</script>

<template>
	<div class="flex justify-between p-2 border-b-2">
		<h2>Cliente: {{ client.fullName }}</h2>
		<div>
			<ActionButton
				class="bg-green-500 rounded ml-4 shadow-2 px-1"
				@click="$emit('submit', client)"
				>Seleccionar</ActionButton
			>
		</div>
	</div>
</template>
