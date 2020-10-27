<template>
  <div class="home">
    <HelloWorld msg="Welcome to Your Vue.js App">
      <template v-slot:luhan="infor">
        <div>name:{{ infor.user.name }}</div>
      </template>
      <template #me>
        <div>
          {{ infor }}
        </div>
      </template>
    </HelloWorld>
    <div class="content">
      <p class="box left">box1</p>
      <p class="box right">box2</p>
    </div>
    <div class="content2">
      <div class="card right">
        <div class="card left">box3</div>
      </div>

      <div class="card right2">
        <div class="card left2">box4</div>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue';
import { reactive, computed, ref } from 'vue';
export default {
  name: 'Home',
  components: {
    HelloWorld
  },
  setup(props, context) {
    console.log(props, context);
    const state = reactive({
      name: 'luhan',
      age: 18,
      sex: 'male'
    });
    const id = ref('12345');
    const myName = computed(() => state.name + ' & liuhuanwei');
    console.log(id, id.value, myName.value);
    window.Listening;
    return {
      state,
      id
    };
  }
};
</script>
<style lang="scss">
:root {
  /* 定义变量 */
  --bgColor: #ff5353;

  /* rgba的四个值分别为：红(R)、绿(G)、蓝(B)、透明度(A) */
  --whiteShadow: -15px -15px 25px rgba(255, 117, 117, 0.5);
  --blackShadow: 15px 15px 25px rgba(110, 40, 40, 0.2);

  --whiteShadow2: 15px 15px 25px rgba(255, 117, 117, 0.5);
  --blackShadow2: -15px -15px 25px rgba(110, 40, 40, 0.2);
}
.content,
.content2 {
  display: flex;
  justify-content: space-around;
  background-color: var(--bgColor);
  align-items: center;
  border-radius: 10px;
}
.box {
  width: 100px;
  height: 100px;
  text-align: center;
  line-height: 100px;
  border-radius: 20px;
  &.left {
    /* 设置外阴影 */
    // box-shadow: var(--blackShadow), var(--whiteShadow);
    box-shadow: inset var(--blackShadow2), inset var(--whiteShadow2);
  }
  &.right {
    /* 设置内阴影 */
    // box-shadow: inset var(--blackShadow), inset var(--whiteShadow);
    box-shadow: var(--blackShadow2), var(--whiteShadow2);
  }
}

.content2 {
  padding: 20px 0;
  .card {
    width: 100px;
    height: 100px;
    text-align: center;
    line-height: 100px;
    border-radius: 200px;
  }
  .left {
    box-shadow: inset var(--blackShadow), inset var(--whiteShadow);
  }

  .right {
    box-shadow: var(--blackShadow), var(--whiteShadow);
    padding: 5px;
  }

  .left2 {
    box-shadow: inset var(--blackShadow2), inset var(--whiteShadow2);
  }

  .right2 {
    box-shadow: var(--blackShadow), var(--whiteShadow);
    padding: 5px;
    // margin: 50px;
  }
}
</style>
