<template>
  <v-container fill-height>
    <v-layout align-center justify-center>

      <div id="forms">
        <v-card>
          <v-tabs v-model="activeTab" color="red darken-4" dark grow slider-color="red accent-1">
            <v-tab v-for="n in tabs.length" :key="n" ripple>
              {{ tabs[n-1] }}

            </v-tab>
            <v-tab-item>
              <LoginComponent></LoginComponent>
            </v-tab-item>
            <v-tab-item>
              <RegisterComponent></RegisterComponent>
            </v-tab-item>
          </v-tabs>
        </v-card>
      </div>

    </v-layout>
    
  </v-container>
</template>

<script lang="ts">
import { Vue, Component } from 'vue-property-decorator';
import LoginComponent from './login.vue';
import RegisterComponent from './register.vue';

@Component({
  components: {
    LoginComponent,
    RegisterComponent
  }
})
export default class AuthComponent extends Vue {
  tabs: string[] = ['Login', 'Sign Up'];
  activeTab: number = 0;

  created() {}
}
</script>

<style lang="scss" scoped>
#forms {
  width: 500px;
}
</style>