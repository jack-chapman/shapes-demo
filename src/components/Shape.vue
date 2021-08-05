<template>
  <div :class="classes" :style="styles"></div>
</template>

<script lang="ts">
import { computed, defineComponent, PropType } from 'vue';

type TopBottom = 'top' | 'bottom';
type RightLeft = 'right' | 'left';

export type CurvePosition = `${TopBottom}-${RightLeft}`;

export type ShapeColour = 'red' | 'emerald' | 'lapis' | 'charcoal' | 'white';

export default defineComponent({
  props: {
    x: Number,
    y: Number,
    curve: String as PropType<CurvePosition>,
    colour: String as PropType<ShapeColour>,
  },
  setup(props) {
    const curveClass = computed(() => {
      return {
        'rounded-tr-full': props.curve === 'top-right',
        'rounded-tl-full': props.curve === 'top-left',
        'rounded-br-full': props.curve === 'bottom-right',
        'rounded-bl-full': props.curve === 'bottom-left',
      };
    });
    const colourClass = computed(() => {
      return {
        'bg-red-500': props.colour === 'red',
        'bg-emerald-500': props.colour === 'emerald',
        'bg-indigo-500': props.colour === 'lapis',
        'bg-true-gray-800': props.colour === 'charcoal',
        'bg-white': props.colour === 'white',
      };
    });
    const styles = computed(() => {
      return {
        gridRow: props.y,
        gridColumn: props.x,
      };
    });
    return {
      classes: {
        ...curveClass.value,
        ...colourClass.value,
      },
      styles,
    };
  },
});
</script>
