<script setup>
const contents = [
	{
		name: "Introduction",
	},
	{
		name: "Present Simple",
	},
	{
		name: "Present Continues",
	},
	{
		name: "Past Simple",
	},
	{
		name: "Infinity, Gerund",
	},
];
</script>
<template>
	<div>
		<div class="p-20">
			<div class="bg-white px-20 py-10">
				<h2 class="text-2xl mb-10 text-center">TABLE OF CONTENTS</h2>
				<div class="grid grid grid-rows-4">
					<div
						v-for="(el, i) in contents"
						class="bg-gradient-to-r from-[#D5DBF280] to-[#CBFDF4CC] mb-5 rounded-[30px] p-5 px-8 flex items-center justify-between cursor-pointer hover:bg-green-200 duration-300">
						<div>
							<span class="bg-[#01756C] p-4 rounded-full text-white">
								0{{ i + 1 }}
							</span>
							{{ el.name }}
						</div>
						<i
							class="bx bx-plus-medical p-4 bg-white rounded-full w-[60px] flex items-center justify-center text-xl cursor-pointer text-[#01756C]"></i>
					</div>
				</div>
			</div>
		</div>
	</div>
</template>

<style lang="scss" scoped></style>
