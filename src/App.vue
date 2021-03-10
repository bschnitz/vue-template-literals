<template>
  <HelloWorld msg="Welcome to Your Vue.js App"/>
</template>

<script>

import { defineAsyncComponent } from 'vue';

const component = 'HelloWorld.vue';

export default {
  name: 'App',
  components: {
    // The following will produce an Error
    HelloWorld : defineAsyncComponent(() => import(`./components/${component}`)),
    // The following works
    // HelloWorld: defineAsyncComponent(() => import('./components/HelloWorld.vue')),
    // The following also works
    /* eslint-disable prefer-template */
    // HelloWorld: defineAsyncComponent(() => import('./components/' + component)),
  },
};
</script>
