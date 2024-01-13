<template>
    <v-container>
        <v-row justify="center">
            <v-col cols="12" md="6">
                <v-card>
                    <v-card-title class="text-h5">
                        Convert Binary to Decimal
                    </v-card-title>
                    <v-card-text>
                        <v-text-field v-model="binaryInput" label="Enter binary number" outlinet></v-text-field>
                        <v-btn @click="convertBinaryToDecimal" color="primary">Convert</v-btn>

                        <v-divider></v-divider>

                        <v-alert v-if="decimalResult !== null" :value="true" type="success">
                            The result in decimal is: {{ decimalResult }}
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
            binaryInput: "",
            decimalResult: null,
        };
    },
    methods: {
        convertBinaryToDecimal() {
            const binaryString = this.binaryInput.trim();

            if (!binaryString.match(/^[0-1]+$/)) {
                alert("Please enter a valid binary number ( 1 or 0)");
                return;
            }

            const decimalResult = parseInt(binaryString, 2);
            this.decimalResult = decimalResult;
        },
    },
};
</script>


<style scoped></style>