<template>
  <Layout class-prefix="layout">
    <Tags :dataSource.sync="tags" @xxx="yyy" />
    <Notes />
    <Types />
    <NumberPad />
  </Layout>
</template>

<script lang="ts  ">
import Vue from 'vue';
import NumberPad from "../components/Money/NumberPad.vue";
import Types from "../components/Money/Types.vue";
import Notes from "../components/Money/Notes.vue";
import Tags from '../components/Money/Tags.vue';
import { Component } from 'vue-property-decorator';
@Component({
    components: { Tags, Notes, Types, NumberPad }
    }
)
export default class Money extends Vue{
     tags = ["衣", "食", "住", "行"];
    yyy(zzz){
       console.log(zzz);
       }

};
</script>

<style lang="scss">
.layout-content {
  display: flex;
  flex-direction: column-reverse;
}
</style>
