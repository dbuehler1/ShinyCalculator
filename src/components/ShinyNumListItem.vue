<template>
  <div v-bind:class="{'bg-success text-light border border-dark': num === testnum}">
    {{this.num}}
  </div>
</template>

<script>
export default {
name: "ShinyNumListItem",
  props : {
    num : Number,
    testnum : Number,
  }
}
</script>

<style scoped>

</style>