<template>
  <div class="box">
    <h1>Printd example</h1>

    <p>
      This is an <b>example!</b> using a <a href="https://vuejs.org/" target="_blank">VueJS</a> <em>component</em>.
    </p>
  
    <a href="https://vuejs.org/" target="_blank"><img src="https://vuejs.org/images/logo.png" width="140" height="140"></a>

    <pre>
      import Printd from 'printd'

      const p: Printd = new Printd()

      p.print(this.$el, `.my_style { color: blue; }`)
    </pre>

    <button @click="print">Print this component</button>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import Component from 'vue-class-component'

import { Printd } from 'printd'

@Component
export default class App extends Vue {

  private d: Printd = new Printd()

  cssText: string = `
    .box {
      font-family: sans-serif;
      width: 500px;
      border: solid 1px #ccc;
      text-align: center;
      padding: 1em;
      margin: 2em auto;
    }

    button {
      background-color: #f0f0f0;
      border: solid 1px #ccc;
      padding: 5px 10px;
      font-size: 12px;
    }

    pre {
      color: #c7254e;
    }
  `

  print (): void {
    this.d.print(this.$el, this.cssText)
  }

}
</script>
<style>
  .box {
    font-family: sans-serif;
    width: 500px;
    border: solid 1px #ccc;
    text-align: center;
    padding: 1em;
    margin: 2em auto;
  }

  button {
    background-color: #f0f0f0;
    border: solid 1px #ccc;
    padding: 5px 10px;
    font-size: 12px;
  }

  pre {
    color: #c7254e;
  }
</style>
