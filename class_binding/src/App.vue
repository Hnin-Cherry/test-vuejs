<template>
<div>
  <div :class="{ active : isActive}">Object Syntax</div>
  
</div>
</template>

<script>


export default {
  name: 'App',
  data() {
    return {
      isActive : true
    }
  }
}
</script>

<style>

.active {
  background-color: blueviolet;
}
</style>
