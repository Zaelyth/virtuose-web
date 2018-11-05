<template>
  <v-form id="form" ref="form" v-model="valid" lazy-validation>
    <v-text-field v-model="email" :rules="emailRules" label="E-mail" required></v-text-field>
    <v-text-field v-model="password" :rules="passwordRules" label="Password" type="password" required></v-text-field>

    <v-btn :disabled="!valid" @click="submit">
      Login
    </v-btn>
  </v-form>
</template>

<script lang="ts">
import { Vue, Component } from 'vue-property-decorator';

@Component
export default class LoginComponent extends Vue {
  valid: boolean = true;

  // Fields
  email: string = '';
  password: string = '';

  // Fields Rules
  emailRules: any[] = [
    (v: string) => !!v || 'E-mail is required',
    (v: string) => /.+@.+/.test(v) || 'E-mail must be valid'
  ];
  passwordRules: any[] = [
    (v: string) => !!v || 'Password is required',
    (v: string) => v.length < 4 || 'Password must be valid'
  ];

  submit() {
    console.log('ok');
  }

  clear() {
    console.log('reset');
  }
}
</script>

<style lang="scss" scoped>
#form {
  padding: 30px;
}
</style>

