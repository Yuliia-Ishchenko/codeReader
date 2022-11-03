<template>
  <HelloWorld />
  <!-- <div class="home">
    <h1>Result deCode: {{testReaderCode}}</h1>
    <StreamBarcodeReader @decode="onDecode" @loaded="onLoaded"></StreamBarcodeReader>
  </div> -->
</template>

<script setup>
import { Options, Vue } from 'vue-class-component';
import HelloWorld from '@/components/HelloWorld.vue'; // @ is an alias to /src
import { StreamBarcodeReader } from "vue-barcode-reader";
import { ref,} from 'vue';
import sound from '@/assets/sounds/beep-07a.mp3'
const testReaderCode = ref();
function onLoaded(result){
  // console.log(result);
}
function onDecode(result){
  // console.log(result);
  testReaderCode.value = result
  var audio = new Audio(sound)
  audio.play()
}
</script>
