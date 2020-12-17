<template>
  <div class="flex flex-col md:flex-row mb-6 rounded md:h-64 w-full">
    <img 
        :src="mountain.image" 
        :alt="mountain.title"         
        class="object-cover rounded-t md:rounded-none md:rounded-l h-full w-full md:w-64">

    <div class="rounded-r p-3">
      <div class="flex items-center justify-between">
        
        <h1 class="text-xl  m-0 mr-3 font-bold">{{ mountain.title }}</h1>
        <p class="text-md rounded bg-green-600 p-2 text-white">{{  format(mountain.updatedAt) }}</p>

      </div>

      <p class="text-md mt-2 text-left">{{  mountain.description }}</p>
    </div>
  </div>
</template>

<script>
  export default {
    props : {
      mountain : {
        type: Object,
        required : true,
        default : () => {

        },
      }
    },
    methods:  {
      format(param) {
        let date = new Date(param);
        let string = date.toString();

        return string.slice(0, 15) + (string.length > 15 ? "" : "");
      },
    }
  };
</script>
<style>

</style>
