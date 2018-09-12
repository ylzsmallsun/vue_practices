<template>
  <div id="app">
      <div>
        <label for="name">What's your name? </label> <input id="name" type="text" v-model="name">
      </div>
      <h1>Hello, <strong>{{ name }}</strong>! Let's learn Vue.js</h1> 
      <div>&#x1f638;</div>

      <div>{{testObj.lan}}</div>
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      name: 'Smallsun',
      testObj: {}
    }
  },
  beforeCreate: function () {
    console.log('----before create-----');
    console.log(this.$el);
    console.log('name: ' + this.name);
  },
  created: function () {
    console.log('----created-----');
    console.log(this.$el);
    console.log('name: ' + this.name);
  },
  beforeMount: function () {
    console.log('----before Mount-----');
    console.log(this.$el);
    console.log('name: ' + this.name);
  },
  mounted: function () {
    console.log('----mounted-----');
    console.log(this.$el);
    console.log('name: ' + this.name);

    // update name and add new property for testObj which is empty object defined in data
    setTimeout(
      ()=> { this.name = '小太阳'; this.testObj.lan='en'; }, 1000);
  },
  beforeUpdate: function () {
    console.log('----before update----');
    console.log(this.$el);
    console.log('name: ' + this.name);
  },
  updated: function () {
    console.log('----updated----');
    console.log(this.$el);
    console.log('name: ' + this.name);
    setTimeout(()=> { this.$destroy()}, 1000);
  },
  beforeDestroy: function () {
    console.log('----before destroy----');
    console.log(this.$el);
    console.log('name: ' + this.name);
  },
  destroyed: function () {
    console.log('---- destroyed----');
    console.log(this.$el);
    console.log('name: ' + this.name);
    window.vm = this;
  }
}
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
}
</style>
