<template>
  <div class="home">
    <h1>{{testReaderCode}}</h1>
    <StreamBarcodeReader @decode="onDecode" @loaded="onLoaded"></StreamBarcodeReader>
    <!-- <HelloWorld msg="Welcome to Your Vue.js + TypeScript App"/> -->
  </div>
</template>

<script setup>
import { Options, Vue } from 'vue-class-component';
import HelloWorld from '@/components/HelloWorld.vue'; // @ is an alias to /src
import { StreamBarcodeReader } from "vue-barcode-reader";
import { ref,} from 'vue';
const testReaderCode = ref();
function onLoaded(result){
  // console.log(result);
}
function onDecode(result){
  // console.log(result);
  testReaderCode.value = result
}
</script>
