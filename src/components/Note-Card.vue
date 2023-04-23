<template>
	<div class="cards-container">
		<div class="card">
			<p class="main-text">
				<slot name="main-text"></slot>
			</p>
			<p class="date"><slot name="date"></slot></p>
		</div>
	</div>
</template>

<style>
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
</style>
