
<template>
    <div class="flex flex-col justify-center items-center ">
        <GoStop @start-game="startGame" @stop-game="stopGame" />
        <ResultsOfGame ref="result" />
    </div>
</template>

<script>
import GoStop from './components/GoStop.vue';
import ResultsOfGame from './components/ResultsOfGame.vue';

export default {
  components: {
    GoStop,
    ResultsOfGame
  },
  methods: {
    startGame() {
      this.$refs.result.startGame();
    },
    stopGame() {
      this.$refs.result.stopGame();
    }
  }
};
</script>
