<template>
  <div class="cesium-container" ref="mapRef" />
</template>
<script setup>
import { ref, defineProps, onMounted } from "vue";
/**
 * You can also import Cesium Object like this
 *
 * import * as Cesium from 'cesium';
 * const viewer = new Cesium.Viewer('cesiumContainer');
 */
import { Viewer } from "cesium";

defineProps({
  msg: String,
});

const mapRef = ref(null);

onMounted(() => {
  const map = new Viewer(mapRef.value);
});
</script>

<style scoped>
.cesium-container {
  width: 100%;
  height: 100%;
  margin: 0 auto;
}
</style>
