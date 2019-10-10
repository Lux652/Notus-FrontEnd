<template>
	<div :class="{ loader: true, fadeout: !isLoading }">
		<img src="../assets/Notus-logo-loading.svg" alt="">
	</div>
</template>

<script>
export default {
	name: "Loading",
	props: ["isLoading"]
};
</script>

<style>

.loader {
	background-color: #081B2F;
	overflow: hidden;
	top: 0;
	left: 0;
	right:0;
	position: fixed;
	display: flex;
	align-items: center;
	justify-content: center;
	height: 100vh;
	opacity:1;
}

.fadeout {
	animation: fadeout 1.5s forwards;
}

@keyframes fadeout {
	to {
	opacity: 0;
	visibility: hidden;
	}
}
</style>