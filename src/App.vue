<template>
   <flex-dome-vue>
     </flex-dome-vue>
</template>
     
<script>
import flexDomeVue from './components/flexDome.vue'
// import go from './components/go.vue'
export default {
  name: 'App',
  components: {
    // go,
    flexDomeVue
  },
  mounted() {
    const fn = function fn(x) {
      return function(y) {
        console.log(y + (++x));
      }
    }
    let f = fn(6);
    f(7);
    f(8);
    f(9);
    f(10);



  },
  methods : {
    //柯里化函数
    add(x, y, fun) {
      console.log(fun(x) + fun(y));
      return fun(x) + fun(y);
    },
    curring() {
      var result = [];
      var add = (...arg) => {
        result = result.concat(arg)
        return add;
      }
      add.valueOf = add.toString = () => {
        return result.reduce((per, cur) => per + cur, 0);
      }
      return add;
    }
  }
}
</script>

<style>
#app {
  width: 100%;
  height: 100%;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

</style>
