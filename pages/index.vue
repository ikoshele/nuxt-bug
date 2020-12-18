<template>
  <component :is="'cointriesList'" :pageData="pageData"></component>
</template>

<script>
export default {
  name: 'index',
  components: {
    'cointriesList': () => import('~/pages/-countries-list'),
  },

  layout() {
    return 'default';
  },
  mixins: [
  ],
  data() {
    return {
      pageData: null,
      template: 'default'
    }
  },
  methods: {
    // async updatePageData() {
    //   let targetCountryName = this.$store.getters.landingActiveCountry.name.toLowerCase();
    //   let url = `${this.$configs.CMS_URL}/countries/slug/${targetCountryName}?lang=${this.$store.$i18n.locale}`;
    //   let pageData = null;
    //   console.log(url)
    //   try {
    //     pageData = await this.$axios.$get(url);
    //     this.pageData = pageData;
    //     history.pushState(null, null, `${this.$store.$i18n.defaultLocale !== this.$store.$i18n.locale ? '/' + this.$store.$i18n.locale : ''}/${this.$namings.SLUG_PARTS.COUNTRY_SLUG_PART}${targetCountryName}`);
    //   } catch (err) {
    //     console.warn('Country not found');
    //   }
    // }
  },
  // fetch(ctx) {
  //   ctx.store.commit('SET_HEADER_TRANSPARENCY', 'true')
  // },
  beforeMount() {
    //this.$store.commit('SET_HEADER_TRANSPARENCY', true);
  },
  created() {
    //this.$nuxt.$on('updatePageEvent', () => {
    //  console.log("EVENT")
    //  this.updatePageData();
    //})
  },
  beforeDestroy() {
    //this.$nuxt.$off('updatePageEvent')
  },
};
</script>

<style>

</style>
