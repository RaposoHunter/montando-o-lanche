<script setup lang="ts">
	import { ref } from "vue";
	import Navbar from "./components/Navbar.vue";
	import SnackPreview from "./components/SnackPreview.vue";
	import SnackSelector from "./components/SnackSelector.vue";

	const hamburger = ref<{
		bread: string | null,
		salads: string[],
		sauces: string[],
		meat: string | null
	}>({
		bread: null,
		salads: [],
		sauces: [],
		meat: null
	});
</script>

<template>
	<Navbar />

	<div class="container">
		<div class="row">
			<SnackPreview :hamburger />
			<SnackSelector :hamburger />
		</div>
	</div>
</template>
