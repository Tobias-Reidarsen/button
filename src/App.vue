<script setup>
import { ref } from "vue";
import CounterBtn from "./components/CounterBtn.vue";

const bool = ref(false);
</script>

<template>
	<main>
		<div class="container">
			<header>
				<h1>Notes</h1>
				<button>+</button>
				<div class="cards-container">
					<div class="card">
						<p class="main-text"></p>
						<p class="date"></p>
					</div>
				</div>
			</header>
		</div>
	</main>
</template>
