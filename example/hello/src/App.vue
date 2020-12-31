<template>
  <div>
    <button @[eventName]="handleClick">确定</button>
    <button v-on:click="handleClick">确定</button>
    <hello-world v-if="flag"></hello-world>
    <div :[attrName]="'id'+id">

    </div>
    <p :id="`id${id}`"></p>
    <div class="test" :class="{'isActive':isActive}" @click.capture="handleClick2">
       <button @[eventName]="handleClick1">确定1</button>
    </div>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";

export default {
  data() {
    return {
      flag: false,
      id:1,
      eventName:"click",
      attrName:"data-id",
      isActive:false
    };
  },
  name: "App",
  components: {
    HelloWorld,
  },
  methods: {
    handleClick() {
      this.flag = !this.flag;
    },
    handleClick1(){
      console.log('click1')
    },
    handleClick2(){
      this.isActive=!this.isActive
      }
  },
  mounted() {},
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.test{
  border:1px solid #d2d2d2;height:40px
}
.isActive{
  border-color:red;
}
</style>
