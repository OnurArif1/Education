<template>
  <div class="form-page">
    <div class="page-wrap">
      <v-snackbar
        v-model="snackbar"
        :timeout="4000"
        location="top right"
        class="notification"
      >
        <div class="action">
          Message Sent
        </div>
        <template #actions>
          <v-btn
            variant="text"
            icon
            @click="snackbar = false"
          >
            <v-icon>mdi-close</v-icon>
          </v-btn>
        </template>
      </v-snackbar>
      <hidden point="mdUp">
        <div class="logo logo-header">
          <nuxt-link :to="routeLink.education.home">
            <img :src="logo" alt="logo">
          </nuxt-link>
        </div>
      </hidden>
      <v-container class="inner-wrap max-md">
        <v-btn
          :to="localePath(routeLink.education.home)"
          icon
          variant="text"
          class="backtohome"
        >
          <i class="ion-ios-home-outline" />
          <i class="ion-ios-arrow-round-back-outline" />
        </v-btn>
        <v-card class="card form-box fragment-fadeUp">
          <div class="full-form-wrap">
            <h3 class="use-text-title title-contact pb-3 text-center">
              {{ $t('common.contact_title2') }}
            </h3>
            <p class="desc use-text-subtitle2 text-center">
              {{ $t('common.contact_subtitle') }}
            </p>
            <div class="form">
              <v-form
                ref="form"
                v-model="valid"
              >
                <v-row class="spacing6">
                  <v-col cols="12" sm="6" class="px-6">
                    <v-text-field
                      v-model="name"
                      :rules="nameRules"
                      :label="$t('common.form_name')"
                      color="white"
                      class="input light"
                      filled
                      required
                    />
                  </v-col>
                  <v-col cols="12" sm="6" class="px-6">
                    <v-text-field
                      v-model="email"
                      :rules="emailRules"
                      :label="$t('common.form_email')"
                      class="input light"
                      color="white"
                      filled
                      required
                    />
                  </v-col>
                  <v-col cols="12" sm="6" class="px-6">
                    <v-text-field
                      v-model="phone"
                      :label="$t('common.form_phone')"
                      color="white"
                      class="input light"
                      filled
                    />
                  </v-col>
                  <v-col cols="12" sm="6" class="px-6">
                    <v-text-field
                      v-model="company"
                      :label="$t('common.form_company')"
                      color="white"
                      class="input light"
                      filled
                    />
                  </v-col>
                  <v-col cols="12" class="px-6">
                    <v-textarea
                      v-model="message"
                      rows="6"
                      color="white"
                      class="input light"
                      filled
                      :label="$t('common.form_message')"
                    />
                  </v-col>
                </v-row>
                <div class="btn-area flex">
                  <div class="form-control-label white-label">
                    <v-checkbox
                      v-model="checkbox"
                      :rules="[v => !!v || 'You must agree to continue!']"
                      :label="$t('common.form_terms')"
                      :hide-details="hideDetail"
                      color="secondary"
                      class="white-label"
                      required
                    />
                    <span>
                      <a href="#" class="link">
                        {{ $t('common.form_privacy') }}
                      </a>
                    </span>
                  </div>
                  <v-btn
                    :block="isMobile"
                    color="secondary"
                    size="large"
                    @click="validate"
                  >
                    {{ $t('common.form_send') }}
                  </v-btn>
                </div>
              </v-form>
            </div>
          </div>
        </v-card>
      </v-container>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import './form-style.scss';
@import '../Title/title-style.scss';
</style>

<script>
import logo from '@/assets/images/education-logo.svg';
import brand from '@/assets/text/brand';
import link from '@/assets/text/link';
import { useLocalePath } from '#imports';
import Hidden from '../Hidden';

export default {
  setup() {
    const localePath = useLocalePath();
    return {
      localePath,
    };
  },
  components: {
    Hidden,
  },
  data() {
    return {
      valid: true,
      snackbar: false,
      name: '',
      nameRules: [v => !!v || 'Name is required'],
      email: '',
      hideDetail: true,
      emailRules: [
        v => !!v || 'E-mail is required',
        v => /.+@.+\..+/.test(v) || 'E-mail must be valid',
      ],
      phone: '',
      company: '',
      message: '',
      checkbox: false,
      logo,
      brand,
      routeLink: link,
    };
  },
  computed: {
    isMobile() {
      const xsDown = this.$vuetify.display.xsAndDown;
      return xsDown;
    },
  },
  methods: {
    async validate() {
      const { valid } = await this.$refs.form.validate();

      if (valid) {
        this.snackbar = true;
        this.hideDetail = true;
      } else {
        this.hideDetail = false;
      }
    },
  },
};
</script>
