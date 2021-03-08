<template>
  <div class="badge">
    <img
      :src="require(`@/assets/${path}`)"
      :alt="alt"
    >
  </div>
</template>

<script>
export default {
  name: "Badge",
  props: {
    path: {
      type: String,
      required: true
    },
    alt: {
      type: String,
      required: true
    },
  },
  
  data() {
    return {
    }
  },
  mounted() {
  },
  methods:{
  }
}
</script>

<style>

</style>