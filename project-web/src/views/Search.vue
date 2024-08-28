<script setup lang="ts">
import { ref, reactive, onMounted } from "vue";
import { useDark } from "@vueuse/core"; // 引入暗黑模式

// const isDark = ref(useDark());
const contact = reactive({
  html_petromyzontidae: "/api/htmls/petromyzontidae/scatter3D-dataset.cdydata.final.html"
})

const screenWidth = ref();
onMounted(() => {
  screenWidth.value = document.body.clientWidth;
  window.onresize = () => {
    screenWidth.value = document.body.clientWidth;
  }
})
</script>

<template>
  <div class="wrapper-background"></div>
  <div class="wrapper-sketch">
    <el-row>
      <el-col :span="2"></el-col>
      <el-col :span="20">
        <el-row>
          <el-col class="wrapper-sketch-text" :span="screenWidth > 1200 ? 14 : 24">
            <div class="wrapper-sketch-text-title">Search</div>
            <div class="wrapper-sketch-text-subtitle">The Page of Search</div>
            <h1 class="wrapper-sketch-text-content">You can search data here.</h1>
          </el-col>
        </el-row>
      </el-col>
      <el-col :span="2"></el-col>
    </el-row>
  </div>
  <!-- 内容 -->
  <!-- 首页内容 -->
  <el-row>
    <el-col :span="2"></el-col>
    <el-col :span="20">
      <el-card class="components-card">
        <h1>3D Petromyzontidae View</h1>
        <iframe
          :style="'width: 100%; height: 680px;'"
          :src="contact.html_petromyzontidae" frameborder="0"></iframe>
      </el-card>
    </el-col>
    <el-col :span="2"></el-col>
  </el-row>
</template>
<style scoped>
.components-card {
  margin-bottom: 50px;
}
</style>