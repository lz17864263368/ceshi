<template>
  <div class="home">
    <button @click="btnclick">点击</button>
    {{frvalue}}
    <img alt="Vue logo" src="../assets/logo.png" />
    <HelloWorld msg="Welcome to Your Vue.js App"  @refsh='changefr' ref="childref"/>
  </div>
</template>

<script setup>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";
import {ref} from 'vue'
const childref=ref('')

const btnclick=()=>{
  console.log('打印了',childref.value.childdata)
  childref.value.childdata='456789'//根据ref更改子组件变量或者调用子组件方法
  console.log('打印了',childref.value.childdata)
  
}
//设置子组件要改变的值
let frvalue=ref('')
const changefr=()=>{
  frvalue.value='子组件触发了父组件的方法'
}
</script>
