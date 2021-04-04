<template>
  <span>
    <component :tag="widget.tag" :is="widget.tag" v-model="proxyModel" v-bind="attributes">
      <template v-if="widget.content">
        <template v-if="typeof widget.content === 'string'">
          {{ widget.content }}
        </template>
        <template v-if="typeof widget.content === 'object'">
          <OfalosRenderer :content="widget.content"/>
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
      type: Object,
      required: true
    },
    value: {
      required: false,
      default: undefined
    }
  },
  data() {
    return {
      x: 'antelope'
    }
  },
  computed: {
    attributes() {
      const { tag, content, ...attributes } = this.widget
      return attributes
    },
    proxyModel: {
      get() {
        return this.value
      },
      set (value) {
        this.$emit('input', value)
      }
    }
  }
}
</script>

<style scoped>

</style>