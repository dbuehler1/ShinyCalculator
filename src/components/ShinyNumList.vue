<template>
  <div class="shiny border border-dark">
    <ShinyNumListItem  v-for="(num, i) in shinyCollection"
                      :key="i"
                      :num="num"
                       :testnum="testNum"
    ></ShinyNumListItem>
  </div>
</template>

<script>
import ShinyNumListItem from "@/components/ShinyNumListItem";
export default {
name: "ShinyNumList",
  props : {
    shinyCollection : Array,
    testNum : Number,
  },
  components: {ShinyNumListItem}
}
</script>

<style scoped>
.shiny {
  background-color: lightgray;
  padding-top: 1rem;
  padding-bottom: 1rem;
  text-align: center;
  margin-left: auto;
  margin-right: auto;
  height: 20rem;
  width: 15rem;
  overflow: auto;
}
</style>