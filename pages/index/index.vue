<template>
  <div>
    <button @click="openConversationList">打开会话列表</button>
    <button @click="openContact">打开联系人</button>
  </div>
</template>
<script>
export default {
  methods: {
    // 打开会话列表
    openConversationList() {
      uni.navigateTo({ url: '/TUIKit/components/TUIConversation/index' });
    },
    // 打开联系人
    openContact() {
      uni.navigateTo({ url: '/TUIKit/components/TUIContact/index' });
    },
  },
};
</script>