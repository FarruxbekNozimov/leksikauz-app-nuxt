<template>
	<div>
		<Header />
		<main class="min-h-screen bg-[#F1F4F6] pt-[75px]">
			<slot />
		</main>
		<Footer />
	</div>
</template>

<script setup>
definePageMeta({
	layout: "default",
});
</script>

<style scoped></style>
