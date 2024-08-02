<script>
import General from '@/components/Forms/General';
import brand from '@/assets/text/brand';
import { defineNuxtComponent } from '#app';

export default defineNuxtComponent({
  components: {
    General,
  },
  head() {
    return {
      title: brand.education.name + ' - General',
    };
  },
});
</script>

<template>
  <div>
    <general />
  </div>
</template>