<template>
  <h1>Headless UI Vue Bug</h1>
  <h2>Scoped Styles</h2>
  <ScopedDialog/>
  <h2>Unscoped Styles</h2>
  <UnscopedDialog/>
</template>

<script lang="ts">
import {defineComponent} from 'vue'
import ScopedDialog from "./components/ScopedDialog.vue";
import UnscopedDialog from "./components/UnscopedDialog.vue";

export default defineComponent({
  name: 'App',
  components: {
    ScopedDialog, UnscopedDialog
  }
})
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
