<template>
  <Layout>
    <div class="tags">
      <router-link
        class="tag"
        v-for="tag in tags"
        :key="tag.id"
        :to="`/labels/edit/${tag.id}`"
      >
        <span>{{ tag.name }}</span>
        <Icon name="right" />
      </router-link>
    </div>
    <div class="createTag-wrapper">
      <Button class="createTag" @click="createTag">新建标签</Button>
    </div>
  </Layout>
</template>

<script lang="ts">
import Vue from "vue";
import { Component } from "vue-property-decorator";
import tagListModel from "../models/tagListModel";
import Button from "../components/Button.vue";
tagListModel.fetch();

@Component({
  components: { Button },
})
export default class Labels extends Vue {
  tags = window.tagList;
  created() {}
  createTag() {
    const name = window.prompt("请输入标签名");
    if (name) {
      const message = tagListModel.create(name);
      if (message === "duplicated") {
        window.alert("标签名重复");
      } else if (message === "success") {
        window.alert("添加成功");
      }
    }
  }
}
</script>

<style lang="scss" scoped>
.tags {
  background: white;
  padding-left: 16px;
  font-size: 16px;
  > .tag {
    min-height: 44px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    border-bottom: 1px solid #e6e6e6;
    > svg {
      margin-right: 16px;
    }
  }
}
.createTag-wrapper {
  text-align: center;
  padding: 16px;
  margin-top: 28px;
}
</style>
