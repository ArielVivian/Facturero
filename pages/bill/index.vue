<script setup>
import { companyName } from '~/data'
// import { client } from '~/data'

//Variables locales

let clientSelected = ref({})

//funciones
function handleSubmit(client) {
	console.log(client)
	clientSelected.value = client
	isModalShow.value = false
}

let isModalShow = ref(false)
</script>

<template>
	<div class="flex justify-center">
		<h2>FACTURA</h2>
	</div>
	<div class="flex justify-center border-b">
		<h2>{{ companyName }}</h2>
	</div>
	<div class="pl-3">
		<ActionButton @click="isModalShow = true">Facturar A:</ActionButton>
		<div class="pt-4">
			<h3>{{ clientSelected.fullName }}</h3>
			<h3>{{ clientSelected.adress }}</h3>
			<h3>{{ clientSelected.postalCode }}</h3>
			<h3>{{ clientSelected.phone }}</h3>
		</div>
	</div>

	<ModalClients v-if="isModalShow" @submit="handleSubmit" />
</template>
