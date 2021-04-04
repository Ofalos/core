<template>
  <span>
    <template v-for="(widget, key) in content">
      <OfalosWrapper :widget="widget" :key="key"
                     v-model="value[widget.key || key]"
                     style="width: 100%"
                     @click="(val) => {$emit('click', val)}"/>
    </template>
  </span>
</template>

<script>
import OfalosWrapper from "./OfalosWrapper.vue"

export default {
  name: "OfalosRenderer",
  components: { OfalosWrapper },
  props: {
    value: {type: Object, required: false, default: () => {return {}}},
    content: { type: [Array, Object], required: true },
  },
  methods: {
    resolve (index, key) {
      const value = JSON.parse(JSON.stringify(this.value))
      if (index) {
        console.log(index, value,  value[index])
      }

    }
  }
}
</script>

<style scoped>

</style>