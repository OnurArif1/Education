<template>
  <div
    ref="wrapper"
    v-scroll="runCounter"
    class="root"
  >
    <v-container class="max-md">
      <v-row class="spacing8 grid">
        <v-col sm="6" class="px-8">
          <title-main
            :head="$t('educationLanding.ourMission_title')"
            :desc="$t('educationLanding.ourMission_desc')"
            align="center"
            color="primary"
          />
        </v-col>
        <v-col sm="6" class="px-8">
          <title-main
            :head="$t('educationLanding.ourVision_title')"
            :desc="$t('educationLanding.ourVision_desc')"
            align="center"
            color="primary"
          />
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<style lang="scss" scoped>
@import 'feature-style.scss';
</style>

<script>
import CountUp from 'vue-countup-v3';
import { ref } from 'vue';
import Title from '../Title';

export default {
  components: {
    'title-main': Title,
    CountUp,
  },
  setup() {
    const visible = ref(false);
    const wrapper = ref(null);
    const offset = 500;
    function runCounter() {
      const scrollPosition = document.documentElement.scrollTop || document.body.scrollTop;
      const topPosition = scrollPosition + offset;

      if (topPosition > wrapper.value.offsetTop) {
        visible.value = true;
      }
    }

    return {
      visible,
      runCounter,
      wrapper,
    };
  },
};
</script>
