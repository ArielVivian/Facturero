<script setup>
import { companyName } from '~/data'
// import { client } from '~/data'

let isModalShow = ref(false)
</script>

<template>
	<div class="flex justify-center">
		<h2>FACTURA</h2>
	</div>
	<div class="flex justify-center border-b">
		<h2>{{ companyName }}</h2>
	</div>
	<ActionButton @click="isModalShow = true">Cliente</ActionButton>
	<ModalClients v-if="isModalShow" />
</template>
