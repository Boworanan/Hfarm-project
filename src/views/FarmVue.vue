<template>
    <div class="home">
      <!-- <img alt="Vue logo" src="../assets/logo.png"> -->
      <FarmComp/>
    </div>
  </template>
  
  <script>
  // @ is an alias to /src
    import FarmComp from '@/components/FarmComp.vue';  
  export default {
    name: 'FarmVue',
    components: {
      FarmComp
    }
  }
  </script>
  