<template>
	<div class="container mx-auto px-6 py-6">

		<div v-if="$fetchState.pending" class="">
			<p class="text-xl text-green-600 my-3 capitalize">
				Fetching mountains...
			</p>

			<ErrorCard v-for="i in [1,2,3,4]"/>
		</div>
  		<p v-else-if="$fetchState.error" class="text-xl text-red-600 my-3">An error occurred :(</p>

  		<div v-else>
  			<div class="flex justify-between items-center mb-4">
  				<div class="flex items-center">
  					<NuxtLink to="/" 
  						class="mr-3 text-green-500"
  						:class="($nuxt.$route.name === 'home') ? 'border-b border-green-600' : ''"
  						>Home /
  					</NuxtLink>
  					<h1 class="text-xl text-green-600">Mountains</h1>
  				</div>
  				<button 
  					v-if="mountains.length > 0" 
  					@click="$fetch" class="px-3 py-2 rounded bg-green-600 text-white">Refresh</button>

  			</div>

  			<div 
  				v-if="mountains.length > 0"
  				class="">
  				
				<Card 
					v-for="mountain in mountains"
					:key="mountain.title"
					:mountain="mountain" 
					/>

  			</div>

  			<div v-else>
  				<h1 class="text-xl text-red-600">No Mountains ....</h1>
  			</div>
  		</div>
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