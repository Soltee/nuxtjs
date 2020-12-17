<template>
	<div class="">
		<div v-for="post in posts" :key="post.id" class="flex flex-col items-start mb-6">

			<div class="flex items-center">
				
				<h1 class="text-xl  m-0 mr-3">{{ post.title }}</h1>
				<p class="text-md rounded bg-green-600 p-2 text-white">{{  format(post.updatedAt) }}</p>

			</div>

			<p class="text-md mt-2">{{  post.description }}</p>

		</div>
	</div>
</template>
<script>
	export default {
		async asyncData({ $axios }) {
			const posts = await $axios.$get(`https://api.nuxtjs.dev/posts`);
			return { posts }
		},
		methods: {
			format(param) {
				return new Date(param);
			}
		}
	};
</script>
<style>
	
</style>