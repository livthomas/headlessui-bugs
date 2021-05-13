<template>
  <button @click="onOpen">Open Scoped Dialog</button>

  <Dialog class="scoped-dialog" :open="open" @close="onClose">
    <DialogOverlay class="scoped-dialog__overlay"></DialogOverlay>

    <div class="scoped-dialog__content">
      <p>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore
        magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo
        consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla
        pariatur.
        Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
      </p>

      <button @click="onClose">Close</button>
    </div>
  </Dialog>
</template>

<script lang="ts">
import {defineComponent, ref} from 'vue'
import {Dialog, DialogOverlay} from "@headlessui/vue";

export default defineComponent({
  name: 'ScopedDialog',
  components: {Dialog, DialogOverlay},
  setup: () => {
    const open = ref(false);

    const onClose = () => open.value = false;
    const onOpen = () => open.value = true;

    return {onClose, onOpen, open}
  }
})
</script>

<style scoped>
.scoped-dialog {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100%;
  width: 100%;
  position: fixed;
  top: 0;
  left: 0;
  z-index: 1000;
}

.scoped-dialog__overlay {
  background-color: rgba(0, 0, 0, 0.25);
  height: 100%;
  width: 100%;
  position: absolute;
}

.scoped-dialog__content {
  background-color: #ffffff;
  box-shadow: 0 32px 48px -16px rgba(0, 0, 0, 0.12);
  max-height: 90vh;
  max-width: 700px;
  padding: 32px;
  text-align: center;
  z-index: 1100;
}
</style>
