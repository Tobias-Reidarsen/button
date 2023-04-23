<script setup>
import { ref } from "vue";

const showModal = ref(false);
</script>
<template>
	<main>
		<div class="overlay">
			<div class="modal">
				<textarea name="node" id="note" cols="30" rows="10"></textarea>
				<button>Add note</button>
				<button class="close">Close</button>
			</div>
		</div>
		<div class="container">
			<header>
				<h1>Notes</h1>
				<button>+</button>
				<div class="cards-container">
					<div class="card">
						<p class="main-text">
							Lorem ipsum dolor sit amet, consectetur adipisicing elit.
							Accusamus dolorum sint quo dolor veritatis itaque!
						</p>
						<p class="date">04/27/3482</p>
					</div>
					<div class="card">
						<p class="main-text">
							Lorem ipsum dolor sit amet, consectetur adipisicing elit.
							Accusamus dolorum sint quo dolor veritatis itaque!
						</p>
						<p class="date">04/27/3482</p>
					</div>
				</div>
			</header>
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
.card {
	width: 225px;
	height: 225px;
	background-color: red;
	padding: 10px;
	border-radius: 15px;
	display: flex;
	flex-direction: column;
	justify-content: space-between;
	margin-right: 20px;
	margin-left: 20px;
}
.date {
	font-size: 12.5px;
	font-weight: bold;
}
.cards-container {
	display: flex;
	flex-wrap: wrap;
}
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
