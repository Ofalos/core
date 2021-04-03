<script>
import Vue from 'vue';
import OfalosRenderer from "../src/lib-components/OfalosRenderer"
// Uncomment import and local "components" registration if library is not registered globally.
// import { CoreSample } from '@/entry.esm';

export default Vue.extend({
  name: 'ServeDev',
  components: { OfalosRenderer },
  data() {
    return {
      content: {
        header: {
          tag: "h1",
          content: "This is a h1 tag",
          style: "background: red; width: 50vw;"
        },
        image: {
          tag: "img",
          src: "https://ik.imagekit.io/hooli/usaifa/tr:h-168/usaifa_-PMdXMUgW.png"
        },
        list: {
          tag: "ul",
          style: "padding-left: 40px;",
          content: [
            {
              tag: "li",
              content: "first",
              style: "color: blue"
            },
            {
              tag: "li",
              content: [
                {
                  tag: "ul",
                  content: [
                    {tag: "li", content: "second sub 1"},
                    {tag: "li", content: "second sub 2"}
                  ]
                }
              ],
              style: "color: gold"
            },
            {
              tag: "li",
              content: "second",
              style: "color: brown"
            },
            {
              tag: "li",
              content: "third",
              style: "color: green"
            }
          ]
        },
        complex: {
          tag: "p",
          content: [
            {tag: "span", content: "I am", style: "color: yellow"},
            {tag: "span", content: "going to london"}
          ]
        }
      }
    }
  }
  // components: {
  //  CoreSample,
  // }
});
</script>

<template>
  <div id="app">
    <OfalosRenderer :content="content"/>
  </div>
</template>
