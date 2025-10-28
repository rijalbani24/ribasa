<template>
  <div>
    <Header />
      <slot />
    <Footer />
  </div>
</template>

<script lang="ts" setup>
import Footer from '~/components/footer.vue';
import Header from '~/components/header.vue';


</script>

<style>

</style>