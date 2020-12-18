<template>
  <CountriesList :posts="fetchedPosts"></CountriesList>
</template>

<script>
import CountriesList from '~/components/CountriesList'

export default {
  name: 'ArchiveFetcher',
  props: {
    listComponentName: {
      type: String,
      required: true,
    }
  },
  data() {
    return {
      fetchingOptions: {
        archiveType: 'countries',
        fields: 'title',
        perPage: 10,
        orderBy: 'date',
        order: 'asc'
      },
      fetchedPosts: [],
    };
  },
  components: {
    CountriesList
    //'CountriesList': () => import('~/components/CountriesList'),
  },
  async fetch() {
    if (process.server) {
      const fields = this.fetchingOptions.fields.replace(/\s/g, '');
      const perPage = this.fetchingOptions.perPage;
      let url = 'http://api-talkremit.test/wp-json/wp/v2/countries?order=asc&orderby=title&per_page=1000&_fields=id,title,link&lang=en '
      console.warn(url, 'Archive fetching');
      try {
        this.fetchedPosts = await this.$axios.$get(url);
      } catch (err) {
        return this.$nuxt.error({statusCode: 404, message: err.message});
      }
      console.log(this.fetchedPosts);
    }
  },
  mounted() {
    //console.warn('MOUNT EVENT')
  }
};
</script>

<style scoped>

</style>
