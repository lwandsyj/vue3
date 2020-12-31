<template>
  <div class="hello">
    hello
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  mounted(){
    console.log("hello component mounted")
  },
   // v3 error  The `destroyed` lifecycle hook is deprecated. Use `unmounted` instead 
  unmounted(){
    console.log("hello component dispose")
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
