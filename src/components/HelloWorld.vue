<template>
  <div>
    <p>子组件内容：{{childdata}}{{msg}}</p>
    <p>
      <button @click="changefather">调用父组件内容</button>
    </p>
  </div>
</template>

<script setup>
import { defineProps,defineExpose,defineEmits,ref,toRefs} from "vue";
//1.父组件传值接收
const props = defineProps({
  //子组件接收父组件传递过来的值
  msg: String,
});
const { msg } = toRefs(props);
let childdata=ref('12345')
// 调用父组件的方法
const emit = defineEmits(["refsh"]);
// emit('refsh')
const changefather=()=>{
   emit('refsh')
}
defineExpose({
  childdata,
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
