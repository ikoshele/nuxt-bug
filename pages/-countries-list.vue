<template>
  <main role="main">
    <ArchiveFetcher :listComponentName="'CountriesList'"></ArchiveFetcher>
  </main>

</template>

<script>
import ArchiveFetcher from '~/components/ArchiveFetcher'
export default {
  props: {
  },
  components: {
    ArchiveFetcher
    //'ArchiveFetcher': () => import('~/components/ArchiveFetcher'),
  },
  watch: {},
  mounted() {
    //console.warn('LIST MOUNT')
  },
  methods: {
    currentProperties: function() {
      if ('ArchiveFetcher') {
        return { listComponentName: 'CountriesList' }
      }
    }
  },

};
</script>

<style>

</style>
