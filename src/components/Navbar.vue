<template>
    <div class="nav">
        <button @click="switchView(true)">Create</button>
        <h1>Battle Bots</h1>
        <button @click="switchView(true)">Collection</button>
    </div>
</template>


<script>
export default {
  data() {
    return {
      showFrom: true
    };
  },
  methods: {
    switchView(val) {
      this.showFrom = val;
    }
  },
  props: ['showForm']
};
</script>



<style>
.nav {
  font-family: monospace, sans-serif;
  color: #fff;
  background-color: #05386b;
  display: flex;
  justify-content: space-evenly;
  align-items: center;
  height: 85px;
}
</style>

