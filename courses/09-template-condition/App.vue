<template>
	<div class="text-center p-8">
		<div class="py-4">
			<h3 class="text-2xl font-semibold">If - else</h3>
			<div v-if="isFirst">Welcome to home page</div>
			<div v-else>Welcome again</div>
			<button class="border border-gray-400 rounded-md py-2 px-4" @click="isFirst = !isFirst">Click me</button>
		</div>

		<div>
			<h3 class="text-2xl font-semibold">If - elseif - else</h3>
			<div v-if="text == 'a'">You typed a</div>
			<div v-else-if="text == 'b'">You typed b</div>
			<div v-else>You didn't type a nor b</div>
			<button class="border border-gray-400 rounded-md py-2 px-4" @click="doIt">Click me</button>
		</div>
	</div>
</template>

<script lang="ts" setup>
import { Ref, ref } from 'vue';

const isFirst: Ref<boolean> = ref(true);
const text: Ref<string> = ref('');

const doIt = () => {
	text.value = prompt('Type the a or b')!;
};
</script>
