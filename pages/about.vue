<template>
  <div class="container">
      <div class="my-3">
        <p v-if="$nuxt.isOffline" class="p-2 text-red-600">Oops! You are offline.</p>
        <p v-if="$nuxt.isOnline" class="p-2 text-green-600">Wooh!.</p>
      </div>
  </div>
</template>

<script>
export default {
	head: {
	  title : 'About',
      // titleTemplate : '%s |',
      htmlAttrs: {
        lang: 'en',
        amp  : true
      },
      bodyAttrs: {
        class : ['dark-mode', 'mobile']
      },// <body class="${}"
      meta: [
        { charset: 'utf-8' },
        { name: 'viewport', content: 'width=device-width, initial-scale=1' },
        { hid: 'description', name: 'description', content: 'Portfolio' }
      ],
      link: [
        { rel: 'icon', type: 'image/x-icon', href: '/favicon.ico' },
        // { rel: 'stylesheet', href: 'https://cdn.jsdelivr.net/npm/@exampledev/new.css@1.1.2/new.min.css' },
      ]
    },
};
</script>

<style>
/* Sample `apply` at-rules with Tailwind CSS
.container {
@apply min-h-screen flex justify-center items-center text-center mx-auto;
}
*/
</style>
