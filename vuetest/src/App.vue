<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <Tree :list="list"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Tree from './components/Tree.vue'
export default {
  // name: 'app',
  components: {
    HelloWorld,
    Tree
  },
  data() {
    return {
        list: [{
          child: [{
            child:[{
              content:"选项1-1-1",
              id: 111,
              type: 1,
              exit: false,
              child:[],
            }],
            content:"选项1-1",
            id: 11,
            type: 0,
            exit: false,
          },{
            content:"选项1-2",
            id: 12,
            type: 1,
            exit: false,
            child:[],
          },{
            content:"选项1-3",
            id: 13,
            type: 1,
            exit: false,
            child:[],
          }],
          content:"选项1",
          id: 1,
          type: 0,
        }, {
          child: [],
          content:"选项2",
          id: 2,
          type: 1,
        }, {
          child: [],
          content:"选项3",
          id: 3,
          type: 1,
        }, {
          child:[{
            content:"选项4-1",
            id: 41,
            type: 1,
            exit: true,
            child:[],
          }],
          content:"选项4",
          id: 4,
          type: 0,
        },
        
        ]
    }
  },

}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
