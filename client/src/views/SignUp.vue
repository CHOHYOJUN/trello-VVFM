<template>
  <v-container fluid>
    <v-slide-y-transition mode="out-in">
      <v-layout column align-center>
      <v-form v-model="valid"
      @submit.prevent="signUp()"
      @keydown.prevent.enter >
        <v-text-field
          label="Username"
          v-model="user.username"
          :rules="notEmptyRules"
          required
        ></v-text-field>
         <v-text-field
          label="Display Name"
          v-model="user.displayName"
          :rules="notEmptyRules"
          required
        ></v-text-field>
        <v-text-field
          label="Password"
          type="password"
          v-model="user.password"
          :rules="notEmptyRules"
          required
        ></v-text-field>
        <v-text-field
          label="Confirm Password"
          type="password"
          v-model="user.confirmPassword"
          :rules="confirmPasswordRules"
          required
        ></v-text-field>
        <v-text-field
          label="Image URL"
          v-model="user.imageUrl"
          :rules="notEmptyRules"
          required
        ></v-text-field>
        <v-btn type="submit" :disabled="!valid">SignUp</v-btn>
      </v-text-field>
    </v-form>
    </v-layout>
    </v-slide-y-transition>
  </v-container>
</template>

<script>
  export default {
    name: 'signUp',
    data: (vm) => ({
      valid: false,
        user: {
          username: '',
          password: '',
          confirmPassword: '',
          displayName: '',
          imageUrl: '',
      },
      notEmptyRules: [(value) => !! value || 'Cannot be value'],
      confirmPasswordRules: [(confirmPassword) => confirmPassword === vm.user.password || 'Password must match'],
    }),
    methods: {
      signUp() {

      }
    }
  }
</script>
