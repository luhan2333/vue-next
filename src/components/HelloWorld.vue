<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
  </div>
  <slot :user="user" name="luhan"> </slot>
  <!-- <slot name="me" :hah="user"></slot> -->
</template>

<script>
import { reactive } from 'vue';
export default {
  setup(props, context) {
    console.log(props, context);
    const user = reactive({
      name: 'luhan',
      sge: 27
    });
    return { user };
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
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
