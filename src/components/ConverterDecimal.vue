<template>
    <v-container>
      <v-row justify="center">
        <v-col cols="12" md="6">
          <v-card>
            <v-card-title>Convert Decimal to Binary</v-card-title>
            <v-card-text>
              <v-text-field v-model="decimalInput" label="Enter decimal number" outlined></v-text-field>
              <v-btn @click="convertDecimalToBinary" color="primary">Convert</v-btn>
  
              <v-divider></v-divider>
  
              <v-alert v-if="binaryResult !== null" :value="true" type="success">
                The result in binary is: {{ binaryResult }}
              </v-alert>
            </v-card-text>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </template>
  
  <script>
  export default {
    data() {
      return {
        decimalInput: "",
        binaryResult: null,
      };
    },
    methods: {
      convertDecimalToBinary() {
        const decimalString = this.decimalInput.trim();
  
        if (isNaN(parseFloat(decimalString))) {
          alert("Please enter a valid decimal number");
          return;
        }
  
        const decimalNumber = parseInt(decimalString, 10);
        const binaryResult = decimalNumber.toString(2);
        this.binaryResult = binaryResult;
      },
    },
  };
  </script>
  