<template>
  <div id="app">
    <router-view />
  </div>
</template>

<script lang="ts">
import { shell } from 'electron'
import Vue from 'vue'
import Component from 'vue-class-component'

@Component
export default class App extends Vue {
  mounted() {
    document.addEventListener('click', (event: any) => {
      if (event.target.tagName === 'A' && event.target.href.startsWith('http')) {
        event.preventDefault()
        shell.openExternal(event.target.href)
      }
    })
  }
}
</script>

<style lang="less" scoped>

</style>


<style>

  /* Global CSS */
  body {
    background: #fff;
    color: #41464b;
  }

  ::-webkit-scrollbar{
    width: 8px;
    height: 6px;
    border-radius: 4px;
    background-color: #fff;

  }
    /*滚动条两端的箭头*/
  ::-webkit-scrollbar-button{
    display: none;
  }
  ::-webkit-scroll-track{
    display: none;
  }
  ::-webkit-scrollbar-track-piece {
    display: none;
  }

  ::-webkit-scrollbar-thumb{
    background-color: #eee;
    opacity: 0.7;
    border-radius: 4px;
  }

  ::-webkit-scrollbar-corner {
    display: none;
  }
  ::-webkit-resizer{
    display: none;
  }

  .github {
    font-size: 16px;
    margin-left: 16px;
    cursor: pointer;
  }

  .logo {
    user-select: none;
  }

  .application {
    font-family: system-ui,-apple-system,BlinkMacSystemFont,Segoe UI,Roboto,Oxygen,Ubuntu,Cantarell,Droid Sans,Helvetica Neue,Fira Sans,sans-serif!important;
  }
</style>
