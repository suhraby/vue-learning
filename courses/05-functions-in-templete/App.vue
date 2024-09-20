<template>
	<div class="text-center p-8">
		<p v-once>{{ msg }}</p>
		<p>{{ isNumberThree(msg) }}</p>
	</div>
</template>

<script lang="ts" setup>
import { ref } from 'vue';
const msg = ref('aha');

const getRandomNumber = (): number => {
	return Math.floor(Math.random() * 3 + 1);
};

msg.value = getRandomNumber().toString();

const isNumberThree = (c: string): string => {
	return +c === 3 ? 'Given number is three' : 'Given number is not three';
};
</script>
