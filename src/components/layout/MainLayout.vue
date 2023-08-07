<script setup>
import TopBar from './TopBar.vue'
import BottomBar from './BottomBar.vue'
</script>

<template>
  <div>
    <TopBar></TopBar>
    <slot></slot>
    <BottomBar></BottomBar>
  </div>
</template>
