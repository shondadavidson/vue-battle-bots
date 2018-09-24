<template>
    <div class="form-container">
      <form v-on:submit.prevent="onSubmit">
      <p>Bot Name* <input type="text" v-model="botName"></p>
      <p>Attack Value* <input type="text" v-model="attack"></p>
      <p>Health Value* <input type="text" v-model="health"></p>
      <br>
      <button @click="createBot(botName, attack, health)">Submit</button>
      <button @click="clearForm">Clear</button>
      </form>
    </div>
</template>


<script>
export default {
  data() {
    return {
      botName: '',
      attack: 0,
      health: 0
    };
  },
  methods: {
    clearForm() {
      this.botName = '';
      this.attack = 0;
      this.health = 0;
    }
  },
  props: ['createBot']
};
</script>

<style>
form {
  margin-top: 50px;
  width: 400px;
  background-color: #fff;
  padding: 10px 20px;
  border-radius: 2px;
  box-shadow: 0 3px 1px -2px rgba(0, 0, 0, 0.2), 0 2px 2px 0 rgba(0, 0, 0, 0.14),
    0 1px 5px 0 rgba(0, 0, 0, 0.12);
}

.form-container {
  width: 100%;
  display: flex;
  justify-content: center;
}
</style>

