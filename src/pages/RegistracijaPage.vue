<template>
  <q-page padding>
    <q-card bordered class="q-pa-md">
      <q-card-section>
        <h2 class="text-h4 text-center">REGISTRACIJA</h2>
      </q-card-section>

      <q-card-section>
        <!-- Korisničko ime -->
        <q-input
          v-model="username"
          label="Korisničko ime"
          outlined
          clearable
          class="q-mb-md"
        />

        <!-- Email -->
        <q-input
          v-model="email"
          type="email"
          label="Email"
          outlined
          clearable
          class="q-mb-md"
        />

        <!-- Lozinka -->
        <q-input
          v-model="password"
          type="password"
          label="Lozinka"
          outlined
          clearable
          class="q-mb-md"
        />
      </q-card-section>

      <q-card-section class="q-mt-md">
        <!-- Registriraj se batun -->
        <q-btn
          label="Registriraj se"
          color="primary"
          unelevated
          @click="registerUser"
        />
      </q-card-section>

      <!-- Natrag batun -->
      <q-btn
        label="Natrag"
        color="secondary"
        icon="arrow_back"
        class="full-width q-mt-lg"
        @click="$router.push('/')"
      />
    </q-card>
  </q-page>
</template>

<script>
import { ref } from "vue";

export default {
  name: "RegistracijaPage",
  setup() {
    const username = ref("");
    const email = ref("");
    const password = ref("");

    const registerUser = () => {
      console.log("Korisničko ime:", username.value);
      console.log("Email:", email.value);
      console.log("Lozinka:", password.value);
      // Implement API or functionality for registering the user
      alert("Registracija uspješna!"); // Placeholder for user feedback
    };

    return {
      username,
      email,
      password,
      registerUser,
    };
  },
};
</script>

<style scoped>
/* Optional Styling */
.q-mb-md {
  margin-bottom: 16px;
}
</style>
