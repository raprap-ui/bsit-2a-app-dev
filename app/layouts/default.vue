<template>
 <v-app>
        <v-navigation-drawer  v-model="drawer"  :rail="rail" permanent  @click="rail = false">
        <template v-slot:prepend>
          <v-list-item
            lines="two"
            prepend-avatar="https://randomuser.me/api/portraits/women/81.jpg"
            subtitle="Logged in"
            title="Jane Smith"
          ></v-list-item>
        </template>

        <v-divider></v-divider>

        <v-list density="compact" nav >
          <v-list-item prepend-icon="mdi-account-group-outline" title="Dashboard" value="Dashboard" to="/dashboard" ></v-list-item >
          <v-list-item prepend-icon="mdi-account-group-outline" title="Prelim" value="Prelim" to="/prelim" ></v-list-item >
          <v-list-item prepend-icon="mdi-account-group-outline" title="Calculate" value="Calculate" to="/calculate"></v-list-item>
          <v-list-item prepend-icon="mdi-account-group-outline" title="ToDo" value="ToDo" to="/Todo"></v-list-item>
  
        </v-list>
        
      </v-navigation-drawer>
      
    <v-app-bar :elevation="2">
  <template v-slot:prepend>
    <v-app-bar-nav-icon @click="drawer = !drawer"  
     > </v-app-bar-nav-icon>
     <v-btn
     @click="drawer = !drawer"
                icon="mdi-chevron-left"
                variant="text"
                @click.stop="rail = !rail"
              ></v-btn>
  </template>

  <v-app-bar-title>Application Bar</v-app-bar-title>
</v-app-bar>
      <v-main>
        <v-container>
        <slot />
        </v-container>
      </v-main>
 </v-app>
</template>

<script setup>
import { ref } from 'vue'
const drawer = ref(true)
  const rail = ref(true)
</script>

<style>

</style>