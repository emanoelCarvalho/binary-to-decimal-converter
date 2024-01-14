<template>
  <v-app>
    <Converter/> 
    <ConverterDecimal/>
  </v-app>
</template>

<script >
import Converter from './components/Converter.vue';
import ConverterDecimal from './components/ConverterDecimal.vue';

export default {
   components: {
    Converter, 
    ConverterDecimal, 
   }
}
</script>
