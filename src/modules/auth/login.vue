<template>
  <form @submit.prevent="submit">
    <v-text-field 
      name="email"
      label="E-mail"
      type="email"
      v-model="email"
      v-validate="'required|email'"
      :error-messages="errors.first('email')"
      required>
    </v-text-field>

    <v-text-field 
      name="password"
      label="Password"
      type="password"
      v-model="password"
      v-validate="'required'"
      :error-messages="errors.first('password')"
      required>
    </v-text-field>

    <v-btn type="submit">
      Login
    </v-btn>
  </form>
</template>

<script lang="ts">
import { Vue, Component } from 'vue-property-decorator';

@Component
export default class LoginComponent extends Vue {
  // Fields
  email: string = '';
  password: string = '';

  submit() {
    this.$validator.validate().then(result => {
      if (!result) {
        return;
      }
    });

    console.log('ok');
  }
}
</script>

<style lang="scss" scoped>
form {
  padding: 30px;
}
</style>

