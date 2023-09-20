<template>
    <loading :active="isLoading" color="#7269ef" :is-full-page="isFullPage" />
  
  </template>
  
  <script>
  import Loading from "vue-loading-overlay";
  import "vue-loading-overlay/dist/vue-loading.css";
  
  export default {
    props: {
      isLoading: {
        type: Boolean,
        default: false,
      },
      isFullPage: {
        type: Boolean,
        default: true,
      },
    },
    components: {
      Loading,
    },
  };
  </script>
  