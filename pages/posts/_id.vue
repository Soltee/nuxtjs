<template>
	<div class="">
		<h1>{{ post.title }}</h1>
		<p>{{  post.description }}</p>
		<p>{{  post.created_at }}</p>
	</div>
</template>
<script>
	export default {
		async asyncData({ params, $axios }) {
			const post = await $axios.$get(`https://api.nuxtjs.dev/posts/${params.id}`);
			return { post }
		}
	};
</script>
<style>
	
</style>