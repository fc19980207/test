<template>
  <ul v-for="item in arr" :key="item">
    <li>{{ item.id }}</li>
    <li>{{ item.title }}</li>
  </ul>
  <div>
    <input type="text" v-model="title" />
  </div>
  <button @click="ck()">点击</button>
</template>

<script>
import { reactive, ref } from "vue";
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  data() {
    return {};
  },
  setup() {
    var arr = reactive([
      { id: 1, title: 123 },
      { id: 2, title: 444 },
      { id: 3, title: 456 },
    ]);
    var title = ref("");
    function ck() {
      //this.title可替换成title.value使用
      var a = { id: arr.length + 1, title: this.title };
      arr.push(a);
      console.log(title);
      this.title = "";
    }
    console.log(arr);
    return { title, ck, arr };
  },
};
</script>
<style scoped>
</style>
