<template>
  <div id="app">
    <p>ElementUI</p>
  <!--  <base-button>Base</base-button>
  <base-button>Not Base</base-button>
  <type-button>成功按钮</type-button> -->
    <reuse-button type="warning">变化按钮</reuse-button>
    <reuse-button type="babab">变化按钮</reuse-button>
    <reuse-button type="primary">变化按钮</reuse-button>
    <reuse-button type="success">变化按钮</reuse-button>
    <reuse-button type="info">变化按钮</reuse-button> 
    <reuse-button type="danger">变化按钮</reuse-button>
    <click-button type="warning" @click="myClick">
    危险按钮---点击
    </click-button>
    <date-paker></date-paker>
    <h1>组件:</h1>
    <pagenation :current="2" :total="40" v-on:myindex="getCurrentIndex"></pagenation>
  </div>
</template>
<script>
import baseButton from "./components/BaseButton.vue";
import TypeButton from "./components/TypeButton.vue";
import ReuseButton from "./components/ReuseButton.vue";
import ClickButton from "./components/ClickButton.vue";
import datePaker from "./components/ElementTest.vue";
import page from './components/page'
import Vue from 'vue'
Vue.use(page);
export default {
  name: 'app',
  components: {
    baseButton,
    TypeButton,
    ReuseButton,
    ClickButton,
    datePaker
  },
  data:function(){
    return {

    }
  },
  methods:{
    myClick(){
      alert("点击一次")
    },
   getCurrentIndex(item){
      console.log(item);
    }
  }
}
</script>

<style scoped>
 
</style>
