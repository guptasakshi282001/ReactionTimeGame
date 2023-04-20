<template>
<div :style="{ backgroundColor: containerColor }" style="width: 900px; height: 450px;"></div>
<button :style="{ backgroundColor: buttonColor }" style="position: absolute; width: 648px; padding: 30px; font-size: 4rem; top: 6%; border-radius: 36px;" @click="startGame">{{ buttonText }}</button>
</template>

     
<script>
export default {
    data() {
        return {
            containerColor: '#2B87D1',
            buttonColor: '#68AE64',
            buttonText: 'Go',
            isChanging: false,
            intervalId: null,
            timeoutId: null
        };
    },
    methods: {
        startColorChange() {
            this.timeoutId = setTimeout(() => {
                this.containerColor = '#008000';
                clearInterval(this.intervalId);
            }, 3000);
        },
        stopColorChange() {
            clearInterval(this.intervalId);
            clearTimeout(this.timeoutId);
            this.containerColor = '#2B87D1';
        },
        startGame() {
            if (this.isChanging) {
                this.stopColorChange();
                this.buttonColor = '#68AE64';
                this.buttonText = 'Go';
                this.$emit('stop-game');
            } else {
                this.intervalId = setInterval(() => {
                    this.containerColor = this.containerColor === '#008000' ? '#2B87D1' : '#008000';
                }, 3000);
                this.buttonColor = '#C86A67';
                this.buttonText = 'Stop';
                this.startColorChange();
                this.$emit('start-game');
            }
            this.isChanging = !this.isChanging;
        }
    }
};
</script>
