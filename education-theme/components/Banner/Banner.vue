<template>
  <div class="hero-content">
    <v-container :class="{ 'fixed-width': isDesktop }">
      <v-row class="banner-wrap">
        <v-col class="px-6" cols="24" lg="24" md="24">
          <div class="banner-text">
            <div class="title">
              <h3 class="use-text-title">
                {{ $t('educationLanding.banner_title') }}
              </h3>
            </div>
            <h5 class="subtitle">
              {{ $t('educationLanding.banner_desc') }}
            </h5>
          </div>
        </v-col>
      </v-row>
    </v-container>
    <div id="watched_counter" />
  </div>
</template>

<style lang="scss" scoped>
@import './banner-style.scss';
</style>

<script>
export default {
  data() {
    return {
      loaded: false,
    };
  },
  computed: {
    isDesktop() {
      const mdDown = this.$vuetify.display.mdAndDown;
      return mdDown;
    },
    isTablet() {
      const smUp = this.$vuetify.display.smAndUp;
      return smUp;
    },
  },
  mounted() {
    this.loaded = true;
  },
};
</script>
