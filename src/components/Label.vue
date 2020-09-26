<template>
  <span class="text-xs font-semibold inline-block py-1 px-2 uppercase rounded text-indigo-600 bg-indigo-200 uppercase last:mr-0 m-1 ">
    {{tag}}
  </span>
</template>

<script>
export default {
  name: "Label",
  props: {
    tag: String
  }
}
</script>

<style scoped>

</style>