<template>
  <div class="container" ref="mapRef" />
</template>
<script setup>
import "mars3d-cesium/Build/Cesium/Widgets/widgets.css" //依赖的cesium库本身css
import "mars3d/dist/mars3d.css";
import { ref, defineProps, onMounted } from "vue";
import * as mars3d from "mars3d";
defineProps({
  msg: String,
});
const mapRef = ref(null);

onMounted(() => {
     var mapOptions = {
     basemaps: [{ name: "天地图", type: "tdt", layer: "img_d", show: true }],
  };
 var map = new mars3d.Map(mapRef.value, mapOptions); //支持的参数请看API文档：http://mars3d.cn/api/Map.html
});
</script>

<style scoped>
.container {
  width: 100%;
  height: 100%;
  margin: 0 auto;
}
</style>
