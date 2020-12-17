<template>
  <div class="container">
    <div>
      <Logo />

      <ul class="m-0 flex items-center my-3">
        <li class="list-none">
          <NuxtLink to="/" class="px-3 py-3 hover:underline" 
            :class="($nuxt.$route.name === 'home') ? 'border-b border-green-600' : ''">
            Home
          </NuxtLink>
        </li>
        <li class="list-none">
          <NuxtLink to="/about" class="px-3 py-3 hover:underline"
            :class="($nuxt.$route.name === 'about') ? 'border-b border-green-600' : ''">
            About
          </NuxtLink>
        </li>
      </ul>
      <div class="my-3">
        <p v-if="$nuxt.isOffline" class="p-2 text-red-600">Oops! You are offline.</p>
        <p v-if="$nuxt.isOnline" class="p-2 text-green-600">Wooh!.</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style>
/* Sample `apply` at-rules with Tailwind CSS
.container {
@apply min-h-screen flex justify-center items-center text-center mx-auto;
}
*/
</style>
