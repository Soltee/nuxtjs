<template>
  <div class="px-6 py-6 max-w-3xl mx-auto">
    <div class="mb-6">
      <Logo />
      <ul class="m-0 flex items-center my-3 justify-center">
        <li class="list-none">
          <NuxtLink to="/" class="mr-8 py-3 hover:underline text-green-600" 
            :class="($nuxt.$route.path === '/') ? 'border-b border-green-600' : ''">
            Home
          </NuxtLink>
        </li>
        <li class="list-none">
          <NuxtLink to="/mountains" class="mr-8 py-3 hover:underline text-green-600"
            :class="($nuxt.$route.name === 'mountains') ? 'border-b border-green-600' : ''">
            Mountains
          </NuxtLink>
        </li>
        <li class="list-none">
          <NuxtLink to="/about" class="mr-8 py-3 hover:underline text-green-600"
            :class="($nuxt.$route.name === 'about') ? 'border-b border-green-600' : ''">
            About
          </NuxtLink>
        </li>
      </ul>
    </div>

    <Nuxt />
  </div>
</template>

<script>
  export default {
    head: {
      title: 'soltee',
      titleTemplate : '%s |',
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
html {
  font-family:
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
}

.button--green {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #3b8070;
  color: #3b8070;
  text-decoration: none;
  padding: 10px 30px;
}

.button--green:hover {
  color: #fff;
  background-color: #3b8070;
}

.button--grey {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #35495e;
  color: #35495e;
  text-decoration: none;
  padding: 10px 30px;
  margin-left: 15px;
}

.button--grey:hover {
  color: #fff;
  background-color: #35495e;
}
</style>
