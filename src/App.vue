<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
    <div>
      <p style="margin-bottom: 24px">
      Current ant-design-vue version: {{ Version }} <br />
      You can change ant-design-vue version on the left panel (Dependencies
      section).
    </p>
    <a-date-picker  />
    </div>
    <router-view/>
  </div>
</template>

<style lang="less">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
#nav {
  padding: 30px;
  a {
    font-weight: bold;
    color: #2c3e50;
    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>

<script lang="ts">
import Vue from 'vue'
import { DatePicker } from 'ant-design-vue';
import { version } from "ant-design-vue/es";

Vue.component(DatePicker.name, DatePicker);
Vue.component(DatePicker.RangePicker.name, DatePicker.RangePicker);

export default class App extends Vue {
  private get Version() {
    return version;
  }
}
</script>
