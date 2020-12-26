<template>
	<div class="w-full">

		<div v-if="$fetchState.pending" class="">
			<p class="text-xl text-green-600 my-3 capitalize">
				Fetching mountain...
			</p>

			<LoadingCard/>

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
  					<h1 class="text-xl text-green-600">{{ mountain.title }}</h1>
  				</div>

  				<div class="flex items-center">
  					
	  				<button 
	  					v-if="mountain && show" 
	  					@click="$fetch" class="px-3 py-2 rounded bg-green-600 text-white">Refresh</button>
	  				<button 
	  					v-else 
	  					@click="show = !show" class="px-3 py-2 rounded bg-green-600 text-white">Show Mountain</button>	
  				</div>

  			</div>

  			<div 
  				v-if="mountain"
  				class="">
  				
				<LazyCard v-if="show"
					:mountain="mountain" 
					/>

  			</div>

  			<div v-else>
  			</div>
  		</div>
	</div>
</template>
<script>
	export default {
		head: {
		    title: 'Mountain',
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
	    	console.log(this.$route.params.id);
	    	const id = this.$route.params.id;
	      	this.mountain = await fetch(
	        	`https://api.nuxtjs.dev/posts/${id}`
	      	).then(res => res.json())
	    },
		data(){
			return {
				show      : true,
				mountain  : {}
			}
		},
	};
</script>
<style>
	
</style>