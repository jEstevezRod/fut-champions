<template>
  <main class="container">
    <div class="flex mb-4">
      <div class="w-1/2">
        <section class="box-container flex flex-wrap flex-row">
          <div
            class="box"
            v-for="(match, index) of matches"
            :key="index"
            :class="{ 'winner': match.win === 'winner', 'looser': match.win === 'looser', 'empty' : match.win === 'empty', 'tie' : match.win === 'tie' }"
            @click="selectMatch(match)"
          >{{match.goalsFavor}} - {{match.goalsContra}}</div>
        </section>
        <section>
          <p class="ml-6">You already played <strong>{{ gamesPlayed }}</strong> games of <strong>30</strong>.</p>
        </section>
      </div>
      <div class="w-1/2">
        <section v-if="Object.entries(matchSelected).length !== 0">
          <form class="px-8 pt-6 pb-8 mb-4 flex flex-wrap  flex-row">
            <div class="mb-4 w-1/2">
              <label class="block text-gray-700 text-sm font-bold mb-2" for="goalsFavor">Goals Favor</label>
              <input
                class="shadow appearance-none border rounded w-20 py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
                id="goalsFavor"
                name="goalsFavor"
                type="number"
                v-model="matchSelected.goalsFavor"
              />
            </div>
            <div class="mb-6 w-1/2">
              <label class="block text-gray-700 text-sm font-bold mb-2" for="goalsContra">Goals Contra</label>
              <input
                class="shadow appearance-none border rounded w-20 py-2 px-3 text-gray-700 mb-3 leading-tight focus:outline-none focus:shadow-outline"
                id="goalsContra"
                name="goalsContra"
                type="number"
                v-model="matchSelected.goalsContra"
              />
            </div>
            <div class="flex items-center justify-between">
              <button
                class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded focus:outline-none focus:shadow-outline"
                type="button"
                @click="storeData"
              >Send</button>
            </div>
          </form>
        </section>
      </div>
     
    </div>
     <div class="flex justify-end" v-if="Object.entries(matchSelected).length !== 0">
        <button @click="unselectMatch" class="bg-red-600 hover:bg-red-700 text-white py-2 px-4 rounded focus:outline-none focus:shadow-outline">Clean match</button>        
      </div>
  </main>
</template>

<script>
export default {
  data() {
    return {
      matchSelected: {},
      matches: [
        { goalsFavor: 1, goalsContra: 0, win: "winner" },
        { goalsFavor: 2, goalsContra: 3, win: "looser" },
        { goalsFavor: 1, goalsContra: 1, win: "tie" },
        { goalsFavor: 0, goalsContra: 0, win: "empty" },
        { goalsFavor: 0, goalsContra: 0, win: "empty" },
        { goalsFavor: 0, goalsContra: 0, win: "empty" },
        { goalsFavor: 0, goalsContra: 0, win: "empty" },
        { goalsFavor: 0, goalsContra: 0, win: "empty" },
        { goalsFavor: 0, goalsContra: 0, win: "empty" },
        { goalsFavor: 0, goalsContra: 0, win: "empty" },
        { goalsFavor: 0, goalsContra: 0, win: "empty" },
        { goalsFavor: 0, goalsContra: 0, win: "empty" },
        { goalsFavor: 0, goalsContra: 0, win: "empty" },
        { goalsFavor: 0, goalsContra: 0, win: "empty" },
        { goalsFavor: 0, goalsContra: 0, win: "empty" },
        { goalsFavor: 0, goalsContra: 0, win: "empty" },
        { goalsFavor: 0, goalsContra: 0, win: "empty" },
        { goalsFavor: 0, goalsContra: 0, win: "empty" },
        { goalsFavor: 0, goalsContra: 0, win: "empty" },
        { goalsFavor: 0, goalsContra: 0, win: "empty" },
        { goalsFavor: 0, goalsContra: 0, win: "empty" },
        { goalsFavor: 0, goalsContra: 0, win: "empty" },
        { goalsFavor: 0, goalsContra: 0, win: "empty" },
        { goalsFavor: 0, goalsContra: 0, win: "empty" },
        { goalsFavor: 0, goalsContra: 0, win: "empty" },
        { goalsFavor: 0, goalsContra: 0, win: "empty" },
        { goalsFavor: 0, goalsContra: 0, win: "empty" },
        { goalsFavor: 0, goalsContra: 0, win: "empty" },
        { goalsFavor: 0, goalsContra: 0, win: "empty" },
        { goalsFavor: 0, goalsContra: 0, win: "empty" }
      ]
    };
  },
  methods: {
    selectMatch(match) {
      this.matchSelected = match;
    },
    unselectMatch() {
      this.matchSelected = {};
    },
    storeData() {
      console.dir(this.matchSelected)
      if ( this.matchSelected.goalsFavor > this.matchSelected.goalsContra) {
        this.matchSelected.win = 'winner';
      } else if (this.matchSelected.goalsFavor < this.matchSelected.goalsContra) {
        this.matchSelected.win = 'looser';
      } else {
        this.matchSelected.win = 'tie'
      }
    }
  },
  computed: {
    gamesPlayed() {
      return this.matches.filter( x => x.win !== 'empty').length
    }
  }
};
</script>

<style scoped>
.container {
  margin: 0 auto;
}
.box {
  height: 50px;
  width: 80px;
  border-radius: 5px;
  background-color: tomato;
  margin: 6px;
  display: flex;
  flex-flow: row wrap;
  justify-content: center;
  align-items: center;
  cursor: pointer;
}
.box-container {
  padding: 20px;
}
.winner {
  background-color: rgb(12, 181, 12);
}
.empty {
  background-color: rgb(51, 121, 164);
}
.looser {
  background-color: rgb(215, 94, 73);
}
.tie {
    background-color: rgb(206, 132, 40);

}
</style>
