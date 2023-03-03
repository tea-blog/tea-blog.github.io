<template>
  <div id="gitalk-container"></div>
</template>
<script lang="ts" setup>
import "gitalk/dist/gitalk.css";
import Gitalk from "gitalk";
import { onMounted } from "vue";
// import { useData } from "vitepress";
// const relativePath = useData().page.value.relativePath;

const gitalk = new Gitalk({
  clientID: "c4894cdcbf39d7dbcfb5",
  clientSecret: "90473f3323b7225c9420d3572ca521bb666c65ed",
  repo: "tea-blog.github.io",
  owner: "tea-blog",
  admin: ["tea-blog"],
  id: location.pathname.substring(0, 50), // Ensure uniqueness and length less than 50
  language: "zh-CN",
  distractionFreeMode: true, // Facebook-like distraction free mode
});

onMounted(() => {
  gitalk.render("gitalk-container");
});
</script>
<style scoped></style>
