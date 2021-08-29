<template>
  <div>
    <v-quagga :onDetected="logIt" :readerSize="readerSize" :readerTypes="['code_128_reader','code_39_vin_reader','code_39_reader']"></v-quagga>
  </div>
</template>

<script>
import Vue from 'vue'
import VueQuagga from 'vue-z-quaggajs';

// register component 'v-quagga'
Vue.use(VueQuagga);

export default {
  name: 'VueBarcodeTest',
  data () {
    return {
      readerSize: {
        width: 640,
        height: 480
      },
      detecteds: []
    }
  },
  methods: {
    logIt (data) {
      console.log('detected', data)
    }

  }
}
</script>