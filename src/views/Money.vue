<template>
  <div>
    <Layout>
      <div class="tags">
        <ul class="current">
          <li class="">衣</li>
          <li class="">食</li>
          <li class="">住</li>
          <li class="">行</li>
        </ul>
      </div>
      <div>
        <label class="notes">
          <span class="name">備註</span>
          <input type="text" />
        </label>
      </div>
      <div>
        <ul class="types">
          <li class="selected">支出</li>
          <li>收入</li>
        </ul>
      </div>
      <div class="numberPad">
        <div class="output">100</div>
        <div class="buttons">
          <button>1</button>
          <button>2</button>
          <button>3</button>
          <button>删除</button>
          <button>4</button>
          <button>5</button>
          <button>6</button>
          <button>清空</button>
          <button>7</button>
          <button>8</button>
          <button>9</button>
          <button>Ok</button>
          <button>0</button>
          <button>.</button>
        </div>
      </div>
    </Layout>
  </div>
</template>

<script lang="ts">
import Layout from "@/components/Layout.vue";
export default {
  components: { Layout },
  name: "Money",
};
</script>
