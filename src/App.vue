<script setup>
import { ref, watch } from "vue";
import ModalBtn from "./components/Modal-btn.vue";
import NoteCard from "./components/Note-Card.vue";

const notes = ref([]);
const showModal = ref(false);

watch(notes.value, (newNote) => {
	console.log(newNote);
});
</script>
<template>
	<main>
		<ModalBtn
			v-if="showModal"
			@hideModalBtn="(n) => (showModal = n)"
			@submit-note="
				(n) => {
					notes.push(n);
					showModal = false;
				}
			"
		></ModalBtn>
		'
		<div class="container">
			<header>
				<h1>Notes</h1>
				<button @click="showModal = true">+</button>
			</header>
			<template v-for="note in notes"
				><NoteCard>
					<template #main-text>{{ note.text }}</template>
					<template #date>{{ note.date }}</template>
				</NoteCard></template
			>
		</div>
	</main>
</template>

<style scoped>
main {
	height: 100vh;
	width: 100vw;
}
.container {
	max-width: 1000px;
	padding: 10px;
	margin: 0 auto;
}
header {
	display: flex;
	justify-content: space-between;
	align-items: center;
}
h1 {
	font-weight: bold;
	margin-bottom: 25px;
	font-size: 75px;
}
header button {
	border: none;
	padding: 10px;
	width: 50px;
	height: 50px;
	cursor: pointer;
	background-color: rgb(21, 20, 20);
	border-radius: 100%;
	color: white;
	font-size: 20px;
}
</style>
