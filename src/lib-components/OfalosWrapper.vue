<template>
  <span>
    <component :is="widget.tag" v-bind="attributes">
      <template v-if="widget.content">
        <template v-if="typeof widget.content === 'string'">
          {{ widget.content }}
        </template>
        <template v-if="typeof widget.content === 'object'">
          <OfalosRenderer :content="widget.content" />
        </template>
      </template>
    </component>
  </span>
</template>

<script>
export default {
  name: "OfalosWrapper",
  props: {
    widget: {
      type: Object
    }
  },
  computed: {
    attributes() {
      const { tag, content, ...attributes } = this.widget
      return attributes
    }
  }
}
</script>

<style scoped>

</style>