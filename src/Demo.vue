<script setup lang="ts">
import domAlign from 'dom-align'
import correctAlign from './align'
import { Fragment } from 'vue-frag'

const alignConfig = {
    points: ['tl', 'bl'],
    overflow: {
      adjustY: 1,
      adjustX: 1,
    },
    useCssTransform: true
  }

function align() {
  const target = document.getElementById('target')
  const source = document.getElementById('source')

  domAlign(source, target, alignConfig)
}

function align2() {
  const target = document.getElementById('target')
  const source = document.getElementById('source')

  correctAlign(source, target, alignConfig)
}

// fragment导致  main 的 parentNode 是一个不在文档流的元素，需要跳过继续找祖先元素， 找到所有 overflow 的

</script>
<template>
  <Fragment>


    <main>
      <button @click="align">align</button>
      <button @click="align2">正确的align</button>
      <div id="source">
        <div>↑点我</div>
        <div>看不见我了</div>
      </div>
      <div class="targetWrapper">
        <button id="target">target的上面应该可以容纳 source</button>
      </div>
    </main>
    <footer>footer</footer>
  </Fragment>
</template>
<style>
#source {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  width: 100px;
  height: 300px;
  background-color: blue;
  color: white;
}

.targetWrapper {
  text-align: center;
}
</style>