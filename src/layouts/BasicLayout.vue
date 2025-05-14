<template>
  <div id="basicLayout">
    <a-space direction="vertical" :style="{ width: '100%' }" :size="[0, 48]">
      <a-layout>
        <a-layout-header class="header">
          <GlobalHeader />
        </a-layout-header>
        <a-layout-content class="content">
          <router-view />
        </a-layout-content>
        <a-layout-footer class="footer">
          <a href="https://github.com/lijianpan1" target="_blank">
            GitHub：路人
          </a>
        </a-layout-footer>
      </a-layout>
    </a-space>
  </div>
</template>

<script setup lang="ts">
import GlobalHeader from "@/components/GlobalHeader.vue";
</script>

<style scoped>
#basicLayout .footer {
  text-align: center;
  bottom: 0;
  left: 0;
  right: 0;
  width: 100%;
  background: #dfdfdf;
  padding: 16px;
}

#basicLayout .header {
  background: #ffffff;
}
</style>
