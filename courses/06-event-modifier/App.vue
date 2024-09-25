<template>
	<div class="text-center p-8 bg-slate-800">
		<div @click.self="writeToConsole">
			<button class="bg-gray-100 p-4">Button</button>
			<!-- <button @click.stop="writeToConsole" class="bg-gray-100 p-4">Button</button> -->
		</div>

		<form @submit.prevent action="post">
			<button>Submit</button>
		</form>

		<button @clicked.right="writeToConsole"></button>
		<button @clicked.left="writeToConsole"></button>
		<button @clicked.middle="writeToConsole"></button>

		<!-- the click event's propagation will be stopped -->
		<a @click.stop="doThis"></a>

		<!-- the submit event will no longer reload the page -->
		<form @submit.prevent="onSubmit"></form>

		<!-- modifiers can be chained -->
		<a @click.stop.prevent="doThat"></a>

		<!-- just the modifier -->
		<form @submit.prevent></form>

		<!-- only trigger handler if event.target is the element itself -->
		<!-- i.e. not from a child element -->
		<div @click.self="doThat">...</div>

		<!-- use capture mode when adding the event listener     -->
		<!-- i.e. an event targeting an inner element is handled -->
		<!-- here before being handled by that element           -->
		<div @click.capture="doThis">...</div>

		<!-- the click event will be triggered at most once -->
		<a @click.once="doThis"></a>

		<!-- the scroll event's default behavior (scrolling) will happen -->
		<!-- immediately, instead of waiting for `onScroll` to complete  -->
		<!-- in case it contains `event.preventDefault()`                -->
		<div @scroll.passive="onScroll">...</div>
	</div>
</template>

<script lang="ts" setup>
import { ref } from 'vue';
const msg = ref('clicked');

const writeToConsole = () => {
	console.log(msg);
};

const doThis = () => {
	console.log(msg);
};

const doThat = () => {
	console.log(msg);
};

const onSubmit = () => {
	console.log(msg);
};

const onScroll = () => {
	console.log(msg);
};
</script>
