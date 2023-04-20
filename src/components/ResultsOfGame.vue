<template>
    <div class="bg-cyan-200 w-5/12 p-5 rounded-3xl m-px  absolute top-52">
        <h2 class="text-2xl mt-5">{{ gameText }}</h2>
        <p class="text-2xl font-medium mt-5">Your HighScore</p>
        <p class="text-2xl">No HighScore Yet.</p>
    </div>
</template>

  <script>
  export default {
    data() {
      return {
        gameText: 'Click Go to Start the Game!'
      };
    },
    methods: {
      startGame() {
        this.gameText = 'Pay attention. Click stop when the color changes.';
      },
      stopGame() {
        this.gameText = 'Click Go to Start the Game!';
      }
    }
  };
  </script>
