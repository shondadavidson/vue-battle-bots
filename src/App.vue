<template>
  <div class="main">
    <div class="nav">
        <button @click="switchView(true)">Create</button>
        <h1>Battle Bots</h1>
        <button @click="switchView(false)">Collection</button>
    </div>
    <section v-if="showForm">
      <bot-form :createBot="createBot" />
    </section>
    <section v-else>
      <div class="header">
        <br>
        <h3 v-if="selectedBots[0]">Bot #1: {{selectedBots[0].botName}}</h3> 
        <h3 v-if="selectedBots[1]">Bot #2: {{selectedBots[1].botName}}</h3>
        <button @click="battle" class="btn">Battle</button>
        <button @click="clearSelected" class="btn">Clear</button>
        <hr>
    </div>
      <collection v-for='(bot, i) in botCollection' 
      :key="i"
      :botObject='bot'
      :deleteBot='() => deleteBot(i)'
      :selectBot='() => selectBot(bot)'
       />
    </section>
  </div>
</template>

<script>
import Navbar from './components/Navbar';
import BotForm from './components/BotForm';
import Collection from './components/Collection';

export default {
  data() {
    return {
      showForm: true,
      botCollection: [],
      selectedBots: []
    };
  },
  methods: {
    switchView(val) {
      this.showForm = val;
    },
    createBot(botName, attack, health) {
      this.botCollection.push({
        botName,
        attack,
        health
      });

      this.botName = '';
      this.attack = 0;
      this.health = 0;

      this.switchView(false);
    },
    deleteBot(i) {
      this.botCollection.splice(i, 1);
    },
    selectBot(bot) {
      if (this.selectedBots.length < 2) {
        this.selectedBots.push(bot);
      } else {
        alert('2 Bots Have Been Selected');
      }
    },
    clearSelected() {
      this.selectedBots = [];
    },
    battle() {
      if (this.selectedBots[0].attack > this.selectedBots[1].attack) {
        alert(`${this.selectedBots[0].botName} wins!`);
      } else {
        alert(`${this.selectedBots[1].botName} wins!`);
      }

      this.selectedBots = [];
    }
  },
  components: {
    Navbar,
    BotForm,
    Collection
  }
};
</script>


<style>
.main {
  font-family: monospace, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  background: #5cdb95;
  min-height: 100vh;
}
</style>

