<script setup>
import { ref } from "vue";

const count = ref(0);

const inc = () => count.value++;
const dec = () => count.value--;
</script>

<!-- <script> //Options version
export default {
	data() {
		return {
			count: 0,
		};
	},
	methods: {
		inc() {
			console.log("inc() called");
			this.count++;
		},
		dec() {
			console.log("dec() called");
			this.count--;
		},
	},
};
</script> -->

<template>
	<main>
		<div>
			<h4>The current count is:</h4>
			<h1>{{ count }}</h1>
			<button @click="dec">-</button>
			<button @click="inc">+</button>
		</div>
	</main>
</template>
