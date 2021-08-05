<template>
  <div :style="style" class="grid">
    <slot />
  </div>
</template>

<script lang="ts">
import { computed, defineComponent } from 'vue';

export default defineComponent({
  props: {
    cols: Number,
    rows: Number,
    size: Number,
  },
  setup(props) {
    const rows = computed(() => `repeat(${props.rows}, ${props.size}px)`);
    const cols = computed(() => `repeat(${props.cols}, ${props.size}px)`);

    const style = computed(() => {
      return {
        gridTemplateRows: rows.value,
        gridTemplateColumns: cols.value,
      };
    });
    return {
      style,
    };
  },
});
</script>
