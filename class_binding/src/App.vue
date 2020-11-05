<template>
<div>
  <div :class="{ active : isActive, 'text-danger' : hasError, static : normal}">Object Syntax</div>
  <div style="margin-top:10px;" :class=" isActive ? 'active' : 'text-danger' ">Second Form</div>
  <button style="padding:10px;margin:10px;" @click="btnToggle()">{{btnLabel}}</button> 

  <div :class="classObject">Computed Syntax</div>

  <ArraySyntax/>
</div>
</template>

<script>
import ArraySyntax from "@/components/ArraySyntax.vue";

export default {
  name: 'App',
  components: {
    ArraySyntax,
  },
  data() {
    return {
      isActive : false,
      btnLabel : 'Active',
      hasError : true,
      normal : true,
      objSyntax : true,
      error : null
    }
  },
  methods: {
    btnToggle() {
      this.isActive = !this.isActive;
      this.btnLabel = !this.isActive ? 'Active' : 'DeActive'; 
    }
  },
  computed: {
    classObject() {
      return {
        active : this.objSyntax && !this.error,
        'text-danger' : this.error && this.error === 'fatal'
      }
    }
  }
}
</script>

<style>

.active {
  background-color : rgb(0, 255, 55);
}
.text-danger {
  background-color: red;
  font-size: 20px;
}
.static {
  font-style: oblique;
}
</style>
