<template>
  <div class="bg-indigo-500 flex p-5">
    <ShapeGrid :cols="3" :rows="4" :size="80">
      <Shape colour="red" curve="top-right" :x="1" :y="1" />
      <Shape colour="white" curve="bottom-left" :x="1" :y="2" />
      <Shape colour="lapis" curve="top-right" :x="2" :y="2" />
      <Shape colour="red" curve="bottom-right" :x="3" :y="3" />
      <Shape colour="charcoal" curve="top-left" :x="1" :y="3" />
      <Shape colour="emerald" curve="bottom-right" :x="2" :y="3" />
      <Shape colour="white" curve="top-right" :x="2" :y="4" />
      <Shape colour="white" curve="top-left" :x="3" :y="2" />
    </ShapeGrid>
    <div class="grid grid-cols-[1fr] grid-rows-[repeat(5,80px)] w-full">
      <div class="row-start-2 flex">
        <div class="bg-white flex items-center w-7/10">
          <h1 class="text-2xl font-bold ml-5">Search by name or category</h1>
        </div>
        <div class="bg-white flex items-center ml-5 w-3/10">
          <h1 class="text-2xl font-bold ml-5">Sort by: Latest</h1>
          <mdi-menu-down class="text-2xl ml-2" />
        </div>
      </div>
    </div>
    <ShapeGrid :cols="3" :rows="4" :size="80">
      <Shape colour="emerald" curve="top-left" :x="1" :y="1" />
      <Shape colour="white" curve="bottom-right" :x="1" :y="2" />
      <Shape colour="lapis" curve="top-right" :x="2" :y="2" />
      <Shape colour="red" curve="bottom-right" :x="3" :y="3" />
      <Shape colour="charcoal" curve="top-left" :x="2" :y="3" />
    </ShapeGrid>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import ShapeGrid from './components/ShapeGrid.vue';
import Shape from './components/Shape.vue';
export default defineComponent({
  name: 'App',
  components: {
    ShapeGrid,
    Shape,
  },
});
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
