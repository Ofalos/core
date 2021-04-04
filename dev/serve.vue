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
        name: { tag: "AInput", type: "text", key: "name" }
      },
      v: { name: "Abdulhakeem", email: "amustapha@hooli.ng" }
    }
  }
  // components: {
  //  CoreSample,
  // }
});
</script>

<template>
  <div id="app">
    <pre>{{v}}</pre>
    <OfalosRenderer :content="content" v-model="v"/>
  </div>
</template>
