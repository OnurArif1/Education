<script>
  import Summer from '@/components/Forms/Summer.vue';
  import brand from 'assets/text/brand';
  import { defineNuxtComponent } from '#app';
  
  export default defineNuxtComponent({
    components: {
      Summer
    },
    head() {
      return {
        title: brand.education.name + ' - Summer '
      }
    }
  })
</script>

<template>
  <div>
    <summer />
  </div>
</template>

<style scoped lang="scss">

</style>