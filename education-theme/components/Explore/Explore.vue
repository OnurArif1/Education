<template>
  <div :class="[isRtl ? 'rtl' : 'ltr']" class="root">
    <div class="card-wrap">
      <v-container :class="{ 'fixed-width': isDesktop }">
        <div v-if="loaded" class="massonry">
          <div>
            <v-row>
              <v-col
                  v-for="(item, index) in categoriesData"
                  :key="index"
                  cols="8"
                  lg="6"
                  sm="8"
                  class="pa-sm-6 pa-2"
              >
                <div
                    :data-aos-delay="index * 200"
                    data-aos="fade-up"
                    data-aos-duration="400"
                >
                  <v-btn 
                      class="category-card" 
                     :to="item.title === $t('educationLanding.englishSummerSchool_title') 
                          ? localePath(link.education.summer) 
                          : item.title === $t('educationLanding.general_title') 
                          ? localePath(link.education.general) 
                          : item.title === $t('educationLanding.ielts_title') 
                          ? localePath(link.education.ielts) 
                          : localePath(link.education.academic)"
                  >
                    <div>
                      <category-card
                        :img="item.img"
                        :title="item.title"
                        :desc="item.desc"
                      />
                    </div>
                  </v-btn>
                </div>
              </v-col>
            </v-row>
          </div>
        </div>
      </v-container>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import './explore-style.scss';
</style>

<script>
import AOS from 'aos';
import imgAPI from '@/assets/images/imgAPI';
import Title from '../Title';
import DotParallax from '../Parallax/Dot';
import CategoryCard from '../Cards/Category';
import {useLocalePath} from "#imports";
import link from '@/assets/text/link';


export default {
  components: {
    'title-main': Title,
    CategoryCard,
    DotParallax,
  },
  setup() {
    const localePath = useLocalePath();
    return {
      localePath
    }
  },
  data() {
    return {
      link,
      loaded: false,
      imgAPI,
      isRtl: false,
      categoriesData: [
        {
          img: imgAPI.avatar[0],
          title: this.$t('educationLanding.englishSummerSchool_title'),
          desc: this.$t('educationLanding.englishSummerSchool_desc'),
        },
        {
          img: imgAPI.avatar[1],
          title: this.$t('educationLanding.general_title'),
          desc: this.$t('educationLanding.general_desc'),
        },
        {
          img: imgAPI.avatar[2],
          title: this.$t('educationLanding.ielts_title'),
          desc: this.$t('educationLanding.ielts_desc'),
        },
        {
          img: imgAPI.avatar[3],
          title: this.$t('educationLanding.academic_title'),
          desc: this.$t('educationLanding.academic_desc'),
        }
      ],
    };
  },
  computed: {
    isDesktop() {
      const mdUp = this.$vuetify.display.mdAndUp;
      return mdUp;
    },
    isMobile() {
      const xsDown = this.$vuetify.display.xsAndDown;
      return xsDown;
    },
  },
  mounted() {
    this.loaded = true;
    AOS.init({
      once: true,
    });
    setTimeout(() => {
      if (this.$vuetify.rtl) {
        this.isRtl = true;
      }
    }, 200);
  },
};
</script>
