<template>
  <div class="d-flex justify-center align-center" style="height: 100vh;">
  
    <v-card width="400" class="text-center">
    <v-icon size="80" color="primary" class="mt-10">mdi-apple </v-icon>
    
     <v-card-text>
      <v-text-field variant="outlined" label="Username" prepend-inner-icon="mdi-account" clearable></v-text-field>
      <v-text-field variant="outlined" flat label="Password" prepend-inner-icon="mdi-lock" type="password" clearable></v-text-field>
   
<v-btn color="primary" @click="login" style="width: 100vh;">Sign </v-btn>
    </v-card-text>
    </v-card>
   
  </div>
</template>

<script setup>
definePageMeta({
    layout: "auth",
});
const defaultUsername = ref ("admin");
const defaultPassword = ref ("admin123")
const username = ref ("");
const password = ref ("");

function login(){
alert("login function called")
}
</script>