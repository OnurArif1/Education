<script>
import Academic from '@/components/Forms/Academic';
import brand from '@/assets/text/brand';
import { defineNuxtComponent } from '#app';

export default defineNuxtComponent({
  components: {
    Academic,
  },
  head() {
    return {
      title: brand.education.name + ' - Academic',
    };
  },
});
</script>

<template>
  <div><academic /></div>
</template>