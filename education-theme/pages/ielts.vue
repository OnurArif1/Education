<script>
import Ielts from '@/components/Forms/Ielts';
import brand from '@/assets/text/brand';
import { defineNuxtComponent } from '#app';

export default defineNuxtComponent({
  components: {
    Ielts,
  },
  head() {
    return {
      title: brand.education.name + ' - Ielts',
    };
  },
});
</script>

<template>
  <div><ielts /></div>
</template>