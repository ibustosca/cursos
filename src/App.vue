<template>
  <div id="app">
    <CoderHeader />
    <CoderCard />
    <CoderFooter />
  </div>
</template>

<script>
import CoderCard from '@/components/CoderCard.vue';
import CoderHeader from '@/components/CoderHeader.vue';
import CoderFooter from '@/components/CoderFooter.vue';

export default {
  name: 'App',
  components: {
    CoderCard,
    CoderHeader,
    CoderFooter,
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
