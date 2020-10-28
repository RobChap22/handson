<template>

</template>

<script lang='ts'>
  import Vue, { PropType } from 'vue';

  export default Vue.extend({
    name: 'Question',
    props: {
      info: {
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
