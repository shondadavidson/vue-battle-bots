<template>
    <div>
    
    <div class="collection">
    <div class="card">
        <p>{{botObject.botName}}</p>
        <p>Attack: {{botObject.attack}}</p>
        <p>Health: {{botObject.health}}</p>
        <button @click="selectBot">Select</button>
        <button @click="deleteBot">Retire</button>
    </div>
    </div>
    </div>
</template>

<script>
export default {
  props: ['botObject', 'deleteBot', 'selectBot']
};
</script>

<style scoped>
.collection {
  margin-top: 25px;
  width: 100%;
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
}
.card {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 300px;
  margin: 25px;
  background-color: #fff;
  color: rgba(0, 0, 0, 0.87);
  border-radius: 2px;
  min-width: 0;
  position: relative;
  text-decoration: none;
  -webkit-box-shadow: 0 2px 1px -1px rgba(0, 0, 0, 0.2),
    0 1px 1px 0 rgba(0, 0, 0, 0.14), 0 1px 3px 0 rgba(0, 0, 0, 0.12);
  box-shadow: 0 2px 1px -1px rgba(0, 0, 0, 0.2), 0 1px 1px 0 rgba(0, 0, 0, 0.14),
    0 1px 3px 0 rgba(0, 0, 0, 0.12);
}
</style>