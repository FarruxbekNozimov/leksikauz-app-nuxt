<script setup>
const focus = ref(false);
const changeFocus = () => (focus.value = !focus.value);
const word = ref("");
const result = ref([]);

const searchWord = async () => {
	word.value = word.value.trim();
	if (word.value.length) {
		const { data } = await useFetch(
			`https://api.dictionaryapi.dev/api/v2/entries/en/${word.value}`
		);
		result.value = data.value;
	}
};

const play = () => {
	var audio = document.getElementById("audio");
	audio.play();
};
</script>
<template>
	<div class="text-center">
		<div class="lg:w-[60%] md:w-[80%] sm:w-[100%] mx-auto mt-8">
			<form
				@submit.prevent="searchWord"
				class="flex bg-white rounded-full p-1 gap-1"
				:class="focus ? 'shadow-xl' : ''">
				<button
					class="flex justify-center items-center text-white bg-[#01756C] rounded-full gap-3 w-[25%] py-4 px-7">
					ENG <img src="/img/arrows-exchange.png" alt="" /> UZB
				</button>
				<div class="flex relative w-full">
					<div
						class="absolute inset-y-0 left-0 flex items-center pl-1 pointer-events-none">
						<svg
							aria-hidden="true"
							class="w-6 h-6 text-gray-500 dark:text-gray-400"
							fill="currentColor"
							viewBox="0 0 20 20"
							xmlns="http://www.w3.org/2000/svg">
							<path
								fill-rule="evenodd"
								d="M8 4a4 4 0 100 8 4 4 0 000-8zM2 8a6 6 0 1110.89 3.476l4.817 4.817a1 1 0 01-1.414 1.414l-4.816-4.816A6 6 0 012 8z"
								clip-rule="evenodd"></path>
						</svg>
					</div>
					<input
						type="text"
						id="simple-search"
						class="bg-gray-50 outline-none text-gray-900 text-sm rounded-full block w-full pl-10 p-2.5"
						placeholder="Search words here..."
						@focus="changeFocus"
						@blur="changeFocus"
						v-model="word" />
				</div>
			</form>
			<div class="py-10 h-[300px]">
				<div v-if="result == null" class="flex">
					<img src="/img/sheksper.png" alt="" />
					<div class="text-center w-full pt-20 px-2">
						<h2 class="text-2xl font-bold my-5">Oops, no such word found!</h2>
						<p class="px-10">
							If you believe there is such a word in the language of
							Shakespeare, please take a few seconds to report it via
							<nuxt-link to="/" class="cursor-pointer text-[#01756C] underline"
								>Telegram</nuxt-link
							>
							or
							<nuxt-link to="/" class="cursor-pointer text-[#01756C] underline"
								>Gmail</nuxt-link
							>
							and we will add it asap!
						</p>
					</div>
				</div>
				<div v-else class="h-full w-full">
					<h2
						v-if="!result.length"
						class="h-full w-[80%] mx-auto flex items-center text-2xl bg-[url('/img/ellipse.png')] bg-center bg-no-repeat text-center">
						Search any words, and we found this word defination, translation and
						etc.
					</h2>
					<div v-else class="h-[330px] p-5 overflow-x-auto">
						<div
							v-for="el in result"
							class="mb-5 shadow-xl bg-white rounded-xl text-start px-10 py-5">
							<h2 class="text-2xl text-bold mb-3">{{ el.word }}</h2>
							<span class="italic text-slate-500">{{
								el.meanings[0]?.partOfSpeech
							}}</span>
							<div class="flex items-center gap-3 py-2">
								<i
									class="bx text-xl cursor-pointer"
									:class="
										el.phonetics[0]?.audio ? 'bx-volume-full' : 'bx-volume-mute'
									"
									@click="() => (el.phonetics[0]?.audio ? play() : 0)"></i>
								<audio id="audio" :src="el.phonetics[0]?.audio"></audio>

								<span class="text-slate-500">{{ el.phonetics[0]?.text }}</span>
							</div>
							<span class="text-md">{{
								el.meanings[0]?.definitions[0]?.definition
							}}</span>
						</div>
					</div>
				</div>
			</div>
		</div>
	</div>
</template>

<style scoped></style>
