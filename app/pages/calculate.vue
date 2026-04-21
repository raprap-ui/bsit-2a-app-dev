<template>
  <div>
    <h1>Calculator</h1>
    <v-card width="500">
      <v-card-text>
        <v-form>
           <v-radio-group v-model="operator" inline>
            <v-radio label="Addition" value="add" />
            <v-radio label="Subtraction" value="sub" />
            <v-radio label="Multiplication" value="mul" />
            <v-radio label="Division" value="div" />
          </v-radio-group>

          <v-text-field label="Enter 1st Number: " v-model="firstnumber"></v-text-field>
           <v-text-field label="Enter 2nd Number: " v-model="secondnumber"></v-text-field>
            <v-text-field label="Total: " v-model="total"></v-text-field>
            <v-btn :label="loading? 'Calculating...' : 'Calculate' " color="primary" @click="calculate">Calculate</v-btn>

        </v-form>
      </v-card-text>
    </v-card>
  </div>
</template>

<script setup>
const firstnumber = ref(0)
const secondnumber = ref(0)
const total = ref(0)
const operator = ref('add')

function calculate() {
  const num1 = Number(firstnumber.value)
  const num2 = Number(secondnumber.value)

  if (operator.value === 'add') {
    total.value = num1 + num2

  } else if (operator.value === 'sub') {
    total.value = num1 - num2

  } else if (operator.value === 'mul') {
    total.value = num1 * num2
    
  } else if (operator.value === 'div') {
    total.value = num2 !== 0 ? num1 / num2 : 'Cannot divide by 0'
  }
}
</script>

<style>

</style>