<template>
  <v-app app dark>
    <auth-component></auth-component>
  </v-app>
</template>

<script>
import AuthComponent from './modules/auth/auth';

export default {
  name: 'App',
  components: { AuthComponent },
  data() {
    return {
      //
    };
  }
};
</script>

<style lang="scss">
.v-messages__message {
  text-align: right;
}
</style>

