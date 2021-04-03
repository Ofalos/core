<template>
  <span>
    <template v-for="(widget, key) in content">
      <OfalosWrapper :widget="widget" :key="key"
                     @click="(val) => {$emit('click', val)}"
                     @input="(val) => {$emit('input', val)}"
                     @blur="(val) => {$emit('blur', val)}"
                     @focus="(val) => {$emit('focus', val)}"
                     style="width: 100%"/>
    </template>
  </span>
</template>

<script>
import OfalosWrapper from "./OfalosWrapper.vue"

export default {
  name: "OfalosRenderer",
  components: { OfalosWrapper },
  props: {
    content: { type: [Array, Object, String], required: true },
  }
}
</script>

<style scoped>

</style>