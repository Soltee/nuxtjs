<template>
	<div class="container mx-auto px-6 py-6">
		<Card 
			v-for="mountain in mountains"
			:key="mountain.title"
			:mountain="mountain" 
			/>
	</div>
</template>
<script>
	export default {
	    async fetch() {
	      this.mountains = await fetch(
	        'https://api.nuxtjs.dev/mountains'
	      ).then(res => res.json())
	    },
		data(){
			return {
				mountains : []
			}
		},
	};
</script>
<style>
	
</style>