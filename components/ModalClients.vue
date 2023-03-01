<script setup>
import { dataClients } from '~/data'

let isModal = ref(false)

const clients = dataClients

const newClient = ref({})

function handleClient(newClient) {
	clients.value.push(newClient)
}
</script>

<template>
	<div
		class="main-modal fixed w-full overflow-hidden flex justify-center items-center animated fadeIn faster pt-8 drop-shadow-xl"
	>
		<div
			class="p-8 shadow-2 border-blue-500 shadow-lg modal-container bg-gray-100 rounded-xl shadow-lg overflow-y-auto"
		>
			<div>
				<ul>
					<Client
						v-for="client in clients"
						:key="client"
						:client="client"
						@submit="$emit('submit', $event)"
					></Client>
				</ul>
				<div class="flex justify-center pt-4">
					<ActionButton
						class="text-sm p-2 bg-green-500 rounded ml-4 shadow-2"
						@click="isModal = true"
						>Nuevo Cliente</ActionButton
					>
				</div>
			</div>
			<div class="pt-4" v-if="isModal">
				<div class="grid grid-cols-2 m-4 gap-4 pt-4 border-t-4 border-black">
					<label>Nombre del cliente:</label>
					<input class="border-x-4" type="text" v-model="newClient.fullName" />
					<label>Direccion:</label>
					<input class="border-x-4" type="text" v-model="newClient.adress" />
					<label>Codigo Postal:</label>
					<input
						class="border-x-4"
						type="text"
						v-model="newClient.postalCode"
					/>
					<label>Telefono:</label>
					<input class="border-x-4" type="text" v-model="newClient.phone" />
				</div>
				<div class="flex justify-center">
					<ActionButton
						class="bg-green-500 rounded ml-4 shadow-2 px-1 mt-4"
						@click="handleClient"
						>Crear Cliente</ActionButton
					>
				</div>
			</div>
		</div>
	</div>
</template>
