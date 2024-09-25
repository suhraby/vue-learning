<template>
	<div class="text-center p-8 bg-slate-800">
		<!-- only call `submit` when the `key` is `Enter` -->
		<input @keyup.enter="submit" />

		<!-- Alt + Enter -->
		<input @keyup.alt.enter="writeToConsole" />

		<!-- Ctrl + Click -->
		<div @click.ctrl="writeToConsole">Do something</div>

		<!-- this will fire even if Alt or Shift is also pressed -->
		<button @click.ctrl="writeToConsole">A</button>

		<!-- this will only fire when Ctrl and no other keys are pressed -->
		<button @click.ctrl.exact="writeToConsole">B</button>

		<!-- this will only fire when no system modifiers are pressed -->
		<button @click.exact="writeToConsole">C</button>
	</div>
</template>

<script lang="ts" setup>
import { ref } from 'vue';
const msg = ref('clicked');

const submit = () => {
	console.log(msg);
};

const writeToConsole = () => {
	console.log(msg);
};
</script>
