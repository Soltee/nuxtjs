<template>
  <div class="container">
    <div>
      <Logo />
      <ul class="m-0 flex items-center my-3">
        <li class="list-none">
          <NuxtLink to="/" class="px-3 py-3 hover:underline" 
            :class="($nuxt.$route.path === '/') ? 'border-b border-green-600' : ''">
            Home
          </NuxtLink>
        </li>
        <li class="list-none">
          <NuxtLink to="/mountains" class="px-3 py-3 hover:underline"
            :class="($nuxt.$route.name === 'mountains') ? 'border-b border-green-600' : ''">
            Mountains
          </NuxtLink>
        </li>
        <li class="list-none">
          <NuxtLink to="/about" class="px-3 py-3 hover:underline"
            :class="($nuxt.$route.name === 'about') ? 'border-b border-green-600' : ''">
            About
          </NuxtLink>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {}
</script>

<style>
/* Sample `apply` at-rules with Tailwind CSS
.container {
@apply min-h-screen flex justify-center items-center text-center mx-auto;
}
*/
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family:
    'Quicksand',
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
