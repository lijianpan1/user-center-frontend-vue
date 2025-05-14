<template>
  <a-row :wrap="false">
    <a-col flex="200px">
      <div class="header-bar">
        <img class="logo" src="../assets/logo.png" alt="logo" />
        <div class="title">路人用户中心</div>
      </div>
    </a-col>
    <a-col flex="auto">
      <a-menu v-model:selectedKeys="current" mode="horizontal" :items="items" />
    </a-col>
    <a-col flex="100px">
      <div class="header-user">
        <a-button type="primary">登 录</a-button>
      </div>
    </a-col>
  </a-row>
</template>
<script setup>
import { h, ref } from "vue";
import {
  MailOutlined,
  AppstoreOutlined,
  SettingOutlined,
} from "@ant-design/icons-vue";
import { useRouter } from "vue-router";

const router = useRouter();

const current = ref(["mail"]);

router.afterEach((to) => {
  current.value = [to.path];
});

const items = ref([
  {
    key: "home",
    icon: () => h(MailOutlined),
    label: "Home",
    title: "Home",
  },
  {
    key: "app",
    icon: () => h(AppstoreOutlined),
    label: "App",
    title: "App",
  },
  {
    key: "sub1",
    icon: () => h(SettingOutlined),
    label: "Navigation Three - Submenu",
    title: "Navigation Three - Submenu",
    children: [
      {
        type: "group",
        label: "Item 1",
        children: [
          {
            label: "Option 1",
            key: "setting:1",
          },
          {
            label: "Option 2",
            key: "setting:2",
          },
        ],
      },
      {
        type: "group",
        label: "Item 2",
        children: [
          {
            label: "Option 3",
            key: "setting:3",
          },
          {
            label: "Option 4",
            key: "setting:4",
          },
        ],
      },
    ],
  },
  {
    key: "alipay",
    label: h(
      "a",
      {
        href: "https://antdv.com",
        target: "_blank",
      },
      "Navigation Four - Link"
    ),
    title: "Navigation Four - Link",
  },
]);
</script>

<style scoped>
.header-bar {
  display: flex;
  align-items: center;
}

.title {
  color: #000000;
  font-size: 16px;
  margin-left: 10px;
}

.logo {
  height: 48px;
}
</style>
