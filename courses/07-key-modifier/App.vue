<template>
	<div class="text-center p-8 bg-slate-800"></div>
</template>

<script lang="ts" setup>
import { ref } from 'vue';

const msg = ref('clicked');

const writeToConsole = () => {
	console.log(msg);
};
</script>
