<template>
  <div>
    <h2 @click='titleOnClick'>{{ news.title }}</h2>
    <p>{{ news.body }}</p>
  </div>
</template>

<script lang='ts'>
  import Vue, { PropType } from 'vue';

  export default Vue.extend({
    name: 'NewsCard',
    props: {
      news: {
        type: Object as PropType<{ title: string; body: string }>,
        required: true
      },
    },
    methods: {
      titleOnClick() {
        this.$emit('titleOnClick')
      }
    }
  });
</script>
