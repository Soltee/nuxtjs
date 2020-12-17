<template>
  <div class="container">
      <div class="my-3">
        <p v-if="$nuxt.isOffline" class="p-2 text-red-600">Oops! You are offline.</p>
        <p v-if="$nuxt.isOnline" class="p-2 text-green-600">Wooh!.</p>
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
