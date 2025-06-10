<!-- 1. 检查 Baseline 流程 Hello World -->
<!-- <template>
  <div>
    <div class="text-red-600 text-3xl">Hello World</div>
  </div>
</template>

<script setup></script>
<style lang="scss" scoped></style> -->

<!--
1.
你的 `bg-opacity-50` 没有效果，是因为 Tailwind CSS 的 `bg-opacity-*` 工具类**只对 `background-color` 有效**，
 而不是对 `bg-slate-800` 这种带有颜色的类直接生效。在 Tailwind v2.x 以后，颜色类已经内置了透明度控制，需要用 `bg-slate-800/50` 这样的写法。
**说明：**
- `bg-slate-800/50` 表示 slate-800 背景色，透明度 50%
- 不再需要单独的 `bg-opacity-50`

2.
三栏横向排列的父容器是flex布局，子元素使用 `flex-1` 来平均分配空间
- `flex-1` 表示子元素在父容器中占据剩余空间
- `mr-5` 用于设置右边距，确保子元素之间有间隔
- `h-screen` 设置容器高度为屏幕高度
- `overflow-hidden` 用于隐藏超出容器的内容

3.
- `bg-cover` 和 `bg-center` 用于设置背景图片的显示方式
- `bg-cover` 表示背景图片覆盖整个容器
- `bg-center` 表示背景图片居中显示

4.
pb-4 是 Tailwind CSS 的一个工具类，用于设置元素的下边距（padding-bottom）为 1rem（16px），
   这通常用于在元素底部添加一些空间，以便内容不会紧贴着底部边缘。
-->


<!-- 2. 可视化大屏 -->
<template>
	<div class="bg-[url('assets/imgs/bg.jpg')] bg-cover bg-center
   h-screen text-white p-5 flex overflow-hidden"
  >
    <!-- 左 -->
		<div class="flex-1 mr-5 bg-slate-800/50 p-3
    flex flex-col">
      <!-- 横向柱状图 -->
      <HorizontalBar class="h-1/3 box-border pb-4" />
      <!-- 雷达图 -->
      <RadarBar class="h-1/3 box-border pb-4" />
      <!-- 关系图 -->
      <Relation class="h-1/3" />

    </div>
    <!-- 中 -->
		<div class="w-1/2 mr-5 flex flex-col">
      <!-- 数据总览图 -->
      <TotalData class="bg-slate-800/50 p-3" />
      <!-- 地图可视化 -->
      <MapChart class="bg-slate-800/50 p-3 mt-4 flex-1" />
    </div>
    <!-- 右 -->
		<div class="flex-1 bg-slate-800/50 p-3
    flex flex-col">
      <!-- 竖向柱状图 -->
      <VerticalBar class="h-1/3 box-border pb-4" />
      <!-- 环形图 -->
      <RingBar class="h-1/3 box-border pb-4" />
      <!-- 文档云图 -->
      <WordCloud class="h-1/3 box-border pb-4" />
    </div>
	</div>
</template>

<script setup>
import HorizontalBar from './components/HorizontalBar.vue'
import RadarBar from './components/RadarBar.vue'
import Relation from './components/Relation.vue'
import TotalData from './components/TotalData.vue'
import MapChart from './components/MapChart.vue'
import VerticalBar from './components/VerticalBar.vue'
import RingBar from './components/RingBar.vue'
import WordCloud from './components/WordCloud.vue'

</script>
<style lang="scss" scoped></style>


<!-- End  原始文件内容 -->
<!-- <script setup>
import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
  <div>
    <a href="https://vite.dev" target="_blank">
      <img src="/vite.svg" class="logo" alt="Vite logo" />
    </a>
    <a href="https://vuejs.org/" target="_blank">
      <img src="./assets/vue.svg" class="logo vue" alt="Vue logo" />
    </a>
  </div>
  <HelloWorld msg="Vite + Vue" />
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style> -->
