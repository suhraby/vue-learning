<template>
	<div class="text-center p-8">
		<h3 class="font-bold text-5xl mb-2">{{ msg }}</h3>
		<button
			class="btn border-blue-700 border-1 rounded-md bg-blue-600 px-8 py-4 text-white text-lg hover:border-blue-800 hover:bg-blue-700"
			@mousemove="click('Mouse has been clicked', $event)"
		>
			Click
		</button>
	</div>
</template>

<script lang="ts" setup>
import { ref } from 'vue';

const msg = ref('Welcome to home page');
const click = (str: string, event: MouseEvent): void => {
	const { clientX, clientY } = event;
	msg.value = `X: ${clientX} - Y: ${clientY}`;

	if (event.currentTarget instanceof HTMLElement) {
		event.currentTarget.style.left = `${clientX - 30}px`;
		event.currentTarget.style.top = `${clientY - 30}px`;
	}
};
</script>

<style>
.btn {
	position: absolute;
}
</style>
