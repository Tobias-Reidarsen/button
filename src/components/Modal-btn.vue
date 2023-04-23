<script setup>
import { watch, reactive } from "vue";
//const note = ref("");
const note = reactive({
	text: "",
	date: new Date(),
});

const emit = defineEmits(["submit-note", "hideModalBtn"]);

const sendNote = function () {
	note.date = new Date();
	emit("submit-note", note);
};
const closeNote = function () {
	emit("hideModalBtn", false);
};

watch(note, (newNote) => {
	console.log(newNote);
});
</script>
<template>
	<div class="overlay">
		<div class="modal">
			<textarea
				name="node"
				id="note"
				cols="30"
				rows="10"
				v-model="note.text"
			></textarea>
			<button @click="sendNote">Add note</button>
			<button class="close" @click="closeNote">Close</button>
		</div>
	</div>
</template>
<style>
.overlay {
	position: absolute;
	width: 100%;
	height: 100%;
	background-color: rgba(0, 0, 0, 0.77);
	z-index: 10;
	display: flex;
	align-items: center;
	justify-content: center;
}
.modal {
	width: 750px;
	background-color: white;
	border-radius: 10px;
	padding: 30px;
	position: relative;
	display: flex;
	flex-direction: column;
}

.modal button {
	padding: 10px 20px;
	font-size: 20px;
	width: 100%;
	background-color: blueviolet;
	border: none;
	color: white;
	cursor: pointer;
	margin-top: 15px;
}
.modal .close {
	background-color: red;
	margin-top: 7px;
}
</style>
