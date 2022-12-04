<template>
  <div>
    <HistogramSlider
      style="margin: 200px auto"
      type="double"
      ref="hist"
      :width="900"
      :bar-height="110"
      :data="data"
      :clip="true"
      :drag-interval="true"
      :hideFromTo="true"
      @finish="finish"
      :force-edges="false"
      :colors="['#4facfe', '#00f2fe']"
      :grid-num="2"
    />
    <a @click.prevent="checkData">click</a>
  </div>
</template>

<script>
import HistogramSlider from './lib//HistogramSlider'
export default {
  data() {
    return {
      data: require('../resources/data.json')
    }
  },
  watch: {
    data() {
      console.log(this.data)
      setTimeout(() => {
        this.$refs.hist.update({ from: Math.min(...this.data), to: Math.max(...this.data) })
      }, 2000)
    }
  },
  methods: {
    finish(val) {
      console.log(val)
    },
    checkData() {
      this.data = [
        1850,
        2090,
        2140,
        2140,
        2330,
        2570,
        2610,
        2660,
        2710,
        2760,
        2760,
        2800,
        2990,
        3040,
        3040,
        3090,
        3090,
        3230,
        3280,
        3280,
        3280,
        3280,
        3330,
        3330,
        3470,
        3470,
        3470,
        3660,
        3990,
        3990,
        4040,
        4040,
        4040,
        4130,
        4230,
        4230,
        4230,
        4230,
        4230,
        4510,
        4510,
        4510,
        4610,
        4610,
        4700,
        4990,
        4990,
        5080,
        5180,
        5270,
        5320,
        5460,
        5650,
        5650,
        5650,
        6120,
        6120,
        6170,
        6170,
        6170,
        6170,
        6220,
        6220,
        6310,
        6410,
        6550,
        6600,
        6600,
        6600,
        6790,
        6840,
        6840,
        6840,
        7070,
        7400,
        7830,
        7830,
        8500,
        8500,
        9350,
        9440,
        11340,
        11860,
        11860,
        13760,
        13760,
        15420,
        16610,
        17320,
        17560,
        18980,
        23860
      ]
    }
  },

  mounted() {
    setTimeout(() => {
      this.$refs.hist.update({ from: Math.min(...this.data[0]), to: Math.max(...this.data[0]) })
    }, 2000)
  },

  components: {
    HistogramSlider
  }
}
</script>
