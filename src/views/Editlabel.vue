<template>
  <Layout>
    <div>
      <Icon name="left" />
      <span>编辑标签</span>
      <Notes field-name="标签名" placeholder="请输入标签名" />
    </div>
  </Layout>
</template>

<script lang="ts">
import { Component } from "vue-property-decorator";
import Vue from "vue";
import tagListModel from "@/models/tagListModel";
import Notes from "@/components/Money/Notes.vue";
@Component({ components: { Notes } })
export default class Editlabel extends Vue {
  created() {
    const id = this.$route.params.id;
    tagListModel.fetch();
    const tags = tagListModel.data;
    const tag = tags.filter((t) => t.id === id)[0];
    if (tag) {
      console.log(tag);
    } else {
      this.$router.replace("/404");
    }
  }
}
</script>

<style lang="scss" scoped></style>
