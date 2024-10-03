<template>
	<div class="text-center p-8">
		<div>
			<input v-model="text" type="text" class="border border-gray-400 rounded-md px-4 py-2" />
			<p class="whitespace-pre-wrap">Value: {{ text }}</p>
			<textarea v-model="text" name="" class="border border-gray-400 rounded-md px-4 py-2"></textarea>
		</div>
		<div class="my-4">
			<p>List values: {{ arrValues }}</p>

			<div class="flex justify-center space-x-4">
				<label for="car">Car</label>
				<input
					type="checkbox"
					id="car"
					v-model="arrValues"
					value="car"
					class="form-checkbox h-5 w-5 text-blue-500 border-gray-300 rounded"
				/>

				<label for="motorbike">Motorbike</label>
				<input
					type="checkbox"
					id="motorbike"
					v-model="arrValues"
					value="motorbike"
					class="form-checkbox h-5 w-5 text-blue-500 border-gray-300 rounded"
				/>

				<label for="truck">Truck</label>
				<input
					type="checkbox"
					id="truck"
					v-model="arrValues"
					value="truck"
					class="form-checkbox h-5 w-5 text-blue-500 border-gray-300 rounded"
				/>
			</div>
		</div>
		<div class="my-4">
			<p>Selected gender is: {{ gender }}</p>
			<div class="flex justify-center space-x-4">
				<label for="male">Male</label>
				<input
					type="radio"
					id="male"
					name="gender"
					v-model="gender"
					value="male"
					class="form-radio h-5 w-5 text-blue-500 border-gray-300 rounded"
				/>

				<label for="female">Female</label>
				<input
					type="radio"
					id="female"
					name="gender"
					v-model="gender"
					value="female"
					class="form-radio h-5 w-5 text-blue-500 border-gray-300 rounded"
				/>
			</div>
		</div>

		<div>
			<p>Selected option is: {{ option }}</p>
			<select class="form-select border-gray-300 rounded" v-model="option">
				<option value="a">Option A</option>
				<option value="b">Option B</option>
				<option value="c">Option C</option>
			</select>
		</div>

		<div>
			<p>{{ text }}</p>
			<input type="text" v-model.trim="text" />
		</div>
	</div>
</template>

<script lang="ts" setup>
import { Ref, ref } from 'vue';

const text = ref('Enter the text');
const arrValues: Ref<string[]> = ref([]);
const gender: Ref<string> = ref('');
const option: Ref<string> = ref('');
</script>

<!-- <template>
	<div class="text-center p-8">
		<input :value="text" type="text" @input="followMe" class="border border-gray-400 rounded-md px-4 py-2" />
		<p>Value: {{ text }}</p>
	</div>
</template>

<script lang="ts" setup>
import { ref } from 'vue';
const text = ref('Enter the text');

const followMe = (e: Event) => {
	if (e.currentTarget instanceof HTMLInputElement) {
		text.value = e.currentTarget.value;
	}
};
</script> -->
