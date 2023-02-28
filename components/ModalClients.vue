<script setup>
import { clients } from '~/data'
</script>

<template>
	<div
		class="main-modal fixed w-full overflow-hidden flex justify-center items-center animated fadeIn faster pt-8"
	>
		<div
			class="p-8 shadow-2 border border-blue-500 shadow-lg modal-container bg-gray-100 rounded-xl shadow-lg overflow-y-auto"
		>
			<div>
				<ul>
					<Client
						v-for="client in clients"
						:key="client"
						:client="client"
					></Client>
				</ul>
			</div>
		</div>
	</div>
</template>
