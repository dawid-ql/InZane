
<template>
    <div class="buttons">
        <section>
            <p>Make life eazy with Zanefy!</p>
            <button @click="playSound1">play1</button>
            <button @click="playSound2">play2</button>
            <button @click="playSound3">play3</button>
            <button @click="playSound4">play4</button>
            <div class="slidecontainer">
                <input  type="range" :model="currentVal" :min="min" :max="max" :value="currentVal" @change="setVolume" class="slider" id="myRange">
            </div>
        </section>
    </div>
</template>

<script>


export default {
    name: "buttons",
    props: {
    },
    data() {
        return {
            min: 1,
            max: 100,
            currentVal: 30
        }
    },
    created() {
    },
    methods: {
        playSound1() {
            this.startAudio("z1");
        },
        playSound2() {
            this.startAudio("z2");
        },
        playSound3() {
            this.startAudio("z3");
        },
         playSound4() {
            this.startAudio("z4");
        },
        setVolume()
        {
            alert(this.currentVal)
        },
        startAudio(fileName) {
            const audio = new Audio(require('@/assets/'+fileName+'.mp3'));
            audio.play();
        }
    },
    computed: {
    },
}
</script>

<style lang="postcss" scoped>
.slidecontainer {
  width: 100%; /* Width of the outside container */
}

/* The slider itself */
.slider {
  -webkit-appearance: none;  /* Override default CSS styles */
  appearance: none;
  width: 100%; /* Full-width */
  height: 25px; /* Specified height */
  background: #d3d3d3; /* Grey background */
  outline: none; /* Remove outline */
  opacity: 0.7; /* Set transparency (for mouse-over effects on hover) */
  -webkit-transition: .2s; /* 0.2 seconds transition on hover */
  transition: opacity .2s;
}

/* Mouse-over effects */
.slider:hover {
  opacity: 1; /* Fully shown on mouse-over */
}

/* The slider handle (use -webkit- (Chrome, Opera, Safari, Edge) and -moz- (Firefox) to override default look) */
.slider::-webkit-slider-thumb {
  -webkit-appearance: none; /* Override default look */
  appearance: none;
  width: 25px; /* Set a specific slider handle width */
  height: 25px; /* Slider handle height */
  background: #4CAF50; /* Green background */
  cursor: pointer; /* Cursor on hover */
}

.slider::-moz-range-thumb {
  width: 25px; /* Set a specific slider handle width */
  height: 25px; /* Slider handle height */
  background: #4CAF50; /* Green background */
  cursor: pointer; /* Cursor on hover */
}
</style>