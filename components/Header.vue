<template>
	<div>
		<header class="bg-[#01756C] h-[75px] fixed w-screen px-20 z-50">
			<div
				class="flex flex-wrap h-full justify-between items-center mx-auto max-w-screen-xl w-full">
				<nuxt-link to="/" class="flex items-center logo">
					<img src="/img/Logo.svg" alt="" />
				</nuxt-link>
				<div class="hidden justify-between items-center lg:flex">
					<ul class="flex gap-8">
						<li>
							<router-link
								to="/en-uz"
								class="flex items-center gap-1 text-white p-4 py-2">
								ENG <img src="/img/arrows-exchange.png" alt="" /> UZB
							</router-link>
						</li>
						<li>
							<router-link
								to="/ru-uz"
								class="flex items-center gap-1 text-white p-4 py-2">
								RUS <img src="/img/arrows-exchange.png" alt="" /> UZB
							</router-link>
						</li>
						<li>
							<router-link
								to="/articles"
								class="flex items-center gap-1 text-white p-4 py-2">
								Articles
							</router-link>
						</li>
						<li>
							<router-link
								to="/grammar"
								class="fromLeft flex items-center gap-1 text-white p-4 py-2">
								Grammar
							</router-link>
						</li>
						<li>
							<router-link
								to="/about"
								class="flex items-center gap-1 text-white p-4 py-2">
								About us
							</router-link>
							<div class=""></div>
						</li>
					</ul>
				</div>
				<button class="block lg:hidden text-5xl text-white">
					<i class="bx bx-menu-alt-right"></i>
				</button>
			</div>
		</header>
	</div>
</template>

<script setup></script>

<style scoped>
.router-link-exact-active {
	font-weight: 800;
	border-bottom: 3px solid lime;
}

.logo {
	text-decoration: none;
	border: none;
}
</style>
