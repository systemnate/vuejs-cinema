<template>
  <div id="movie-filter">
    <h2>Filter results</h2>
    <div class="filter-group">
      <check-filter v-for="genre in genres" v-bind:title="genre" v-on:check-filter="checkFilter"></check-filter>
    </div>
  </div>
</template>

<script>
  import CheckFilter from './CheckFilter.vue';
  import genres from '../util/genres';

  export default {
    components: {
      CheckFilter
    },
    data() {
      return {
        genres
      };
    },
    methods: {
      checkFilter(category, title, checked) {
        this.$emit('check-filter', category, title, checked);
      }
    }
  }
</script>
