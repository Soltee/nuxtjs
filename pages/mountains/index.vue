<template>
	<div class="w-full">

		<div v-if="$fetchState.pending" class="">
			<p class="text-xl text-green-600 my-3 capitalize">
				Fetching mountains...
			</p>

			<LoadingCard v-for="(i, index) in [1,2,3,4]" :key="index"/>
		</div>
  		<p v-else-if="$fetchState.error" class="text-xl text-center text-red-600 my-8">An error occurred :(</p>

  		<div v-else class="w-full">
  			<div class="w-full flex justify-between mb-4">
  				<div class="flex items-center">
  					<NuxtLink to="/" 
  						class="mr-3 text-green-500"
  						:class="($nuxt.$route.name === 'home') ? 'border-b border-green-600' : ''"
  						>Home /
  					</NuxtLink>
  					<h1 class="text-xl text-green-600">Mountains</h1>
  				</div>

  				<div class="flex items-center">
  					
	  				<button 
	  					v-if="mountains.length > 0 && show" 
	  					@click="$fetch" class="px-3 py-2 rounded bg-green-600 text-white">Refresh</button>
	  				<button 
	  					v-else 
	  					@click="show = !show" class="px-3 py-2 rounded bg-green-600 text-white">Show Mountains</button>	
  				</div>

  			</div>

  			<div 
  				v-if="mountains.length > 0"
  				class="">
  				
				<LazyCard v-if="show"
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
		head: {
		    title: 'Mountains',
		    meta: [
		      { charset: 'utf-8' },
		      { name: 'viewport', content: 'width=device-width, initial-scale=1' },
		      { 
		      	hid: 'description',//make sure to load only one
		      	name: 'description', content: 'Beautiful Mountains around the world.' }
		    ],
		    link: [
		      { rel: 'icon', type: 'image/x-icon', href: '/favicon.ico' }
		    ]
		  },
	    async fetch() {
	      this.mountains = await fetch(
	        'https://api.nuxtjs.dev/posts'
	      ).then(res => res.json())
	    },
		data(){
			return {
				show      : true,
				mountains : []
			}
		},
	};
</script>
<style>
	
</style>