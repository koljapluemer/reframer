<template>
  <div v-if="showProblemInput">
    <h2>Jot down a problem:</h2>
    <input name="" id="" cols="30" rows="10" v-model="problem">
  </div>
  <div v-else>
    <h3>
      Reframe {{ problem }} into {{ frame }}:
    </h3>
  </div>

  <button @click="reframe()">Reframe!</button>
  <button @click="showProblemInput = !showProblemInput">Toggle Problem Input</button>
</template>

<script >
export default {
  name: "HomeView",
  components: {},
  data() {
    return {
      problem: "",
      showProblemInput: true,
      frames: [
        'Algorithm',
        'SMART Goal',
        'Business Model Canvas',
        'Ockham\'s Razor',
      ],
      frame: null
    };
  },
  methods: {
    reframe() {
      this.showProblemInput = false;
      this.frame = this.frames[Math.floor(Math.random() * this.frames.length)];
    },
  },
  computed: {},
  mounted() {},
  beforeDestroy() {},
};
</script>
