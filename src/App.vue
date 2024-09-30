<script setup lang="ts">
	import { ref } from "vue";
	import Navbar from "./components/Navbar.vue";
	import SnackPreview from "./components/SnackPreview.vue";
	import SnackSelector from "./components/SnackSelector.vue";
	import UserForm from "./components/UserForm.vue";
	import OrderConfirmed from "./components/OrderConfirmed.vue";

	const step = ref(1);

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

	const user = ref<{
		name: string | null,
		address: string | null
	}>({
		name: null,
		address: null
	});

	function handleNewOrder()
	{
		step.value = 1;
		hamburger.value = {
			bread: null,
			salads: [],
			sauces: [],
			meat: null
		};
		user.value = {
			name: null,
			address: null
		};
	}
</script>

<template>
	<Navbar />

	<div class="container">
		<div class="row">
			<SnackPreview :hamburger />
			<SnackSelector v-if="step === 1" :step :hamburger @snack-selected="step = 2" />

			<UserForm v-if="step === 2" :user @user-returned="step = 1" @user-submitted="step = 3"/>

			<OrderConfirmed v-if="step === 3" @repeat-order="step = 1" @new-order="handleNewOrder"/>
		</div>
	</div>
</template>
