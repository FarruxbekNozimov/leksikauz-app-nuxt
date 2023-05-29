<script setup>
const latest = [
	{ title: "Ingliz tilidagi so'zlarni eslab qolishing 11 ta samarali usuli" },
	{ title: "Ingliz tilini samarali o'rganish uchun 7 ta maslahat" },
	{ title: "O‘zbek tilining asosiy imlo qoidalari" },
	{ title: "Upwork'da ish boshlash" },
	{ title: "Most Confused Words in English" },
	{ title: "Most Confused Words in English" },
];
</script>
<template>
	<div>
		<div class="px-20 py-10">
			<div class="relative flex justify-between gap-5">
				<div class="w-[60%]">
					<form>
						<label
							for="default-search"
							class="mb-2 text-sm font-medium text-gray-900 sr-only dark:text-white"
							>Search</label
						>
						<div class="relative">
							<div
								class="absolute inset-y-0 left-0 flex items-center pl-3 pointer-events-none">
								<svg
									aria-hidden="true"
									class="w-5 h-5 text-gray-500 dark:text-gray-400"
									fill="none"
									stroke="currentColor"
									viewBox="0 0 24 24"
									xmlns="http://www.w3.org/2000/svg">
									<path
										stroke-linecap="round"
										stroke-linejoin="round"
										stroke-width="2"
										d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z"></path>
								</svg>
							</div>
							<input
								type="search"
								id="default-search"
								class="block w-full p-4 pl-10 text-sm text-gray-900 border border-gray-300 rounded-2xl bg-gray-50 focus:ring-blue-500 focus:border-blue-500 outline-none"
								placeholder="Search articles here..."
								required />
						</div>
					</form>
					<nuxt-link
						v-for="el in 10"
						:to="`articles/${el}`"
						class="cursor-pointer rounded-2xl shadow-xl mt-5 bg-white flex justify-between">
						<img src="/book.png" alt="" class="w-[40%]" />
						<div class="w-[60%] p-5">
							<div class="flex items-center gap-10">
								<div class="flex items-center text-sm gap-2 text-slate-700">
									<i class="bx bxs-calendar"></i>
									<span>1 month ago</span>
								</div>
								<div class="flex items-center text-sm gap-2 text-slate-700">
									<i class="bx bx-book-open"></i>
									<span>number of reads: 52</span>
								</div>
							</div>
							<h2 class="py-5 text-md">
								Ingliz tilidagi so'zlarni eslab qolishing 11 ta samarali usuli
							</h2>
							<p class="text-sm">
								Chet tilini o’rganishda so’z boyligini doimiy ravishda boyitib
								borish, ya’ni ko’proq yangi so’zlarni yod olish, juda muhimdir.
								Biroq, hamma ham bu ishni uddalay olmaydi. So’z boyligini
								oshirish ...
							</p>
						</div>
					</nuxt-link>
				</div>
				<div class="h-full w-[40%]">
					<h2 class="text-xl font-bold text-start p-5 pl-0">Latest articles</h2>
					<div class="bg-white">
						<ul class="list-disc text-slate-500">
							<li class="ml-5 mb-5 text-md" v-for="el in latest">
								{{ el.title }}
							</li>
						</ul>
					</div>
				</div>
			</div>
		</div>
	</div>
</template>

<style lang="scss" scoped></style>
