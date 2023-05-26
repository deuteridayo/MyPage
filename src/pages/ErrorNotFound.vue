<template>
  <q-page class="text-center q-pa-md flex flex-center">
    <div>
      <div style="color: #9090ff; font-size: 30vh">404</div>

      <div class="text-h1" style="opacity: 0.6">ごめんね</div>

      <q-btn
        class="q-mt-xs"
        flat
        color="white"
        text-color="blue"
        unelevated
        style="font-size: 5vh"
        to="/"
        label="あきらめる"
        no-caps
      />
    </div>
  </q-page>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'ErrorNotFound',

  setup() {
    const color = () => {
      return 'indigo-3';
    };

    return {
      color,
    };
  },
});
</script>
