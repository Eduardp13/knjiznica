<template>
  <q-page padding>
    <q-card bordered class="q-pa-md">
      <div class="q-pa-md">
        <h2 class="text-h4 text-center">PRIJAVA</h2>

        <q-form @submit="submitLogin" class="q-gutter-md">
          <!-- Korisničko ime -->
          <q-input
            v-model="username"
            filled
            label="Korisničko ime"
            hint="Unesite vaše korisničko ime"
          />

          <!-- Lozinka -->
          <q-input
            v-model="password"
            filled
            type="password"
            label="Lozinka"
            hint="Unesite vašu lozinku"
          />

          <!-- Potvrdi batun -->
          <q-btn label="Potvrdi" type="submit" color="primary" unelevated />
        </q-form>

        <!-- Natrag batun -->
        <q-btn
          label="Natrag"
          color="secondary"
          icon="arrow_back"
          class="full-width q-mt-lg"
          @click="$router.push('/')"
        />
      </div>
    </q-card>
  </q-page>
</template>

<script>
import { ref } from "vue";

export default {
  name: "LoginPage",
  setup() {
    const username = ref("");
    const password = ref("");

    function submitLogin() {
      if (username.value && password.value) {
        alert(`Dobrodošli, ${username.value}!`);
      } else {
        alert("Molimo unesite korisničko ime i lozinku.");
      }
    }

    return {
      username,
      password,
      submitLogin,
    };
  },
};
</script>

<style scoped>
.full-width {
  width: 100%;
}
</style>
