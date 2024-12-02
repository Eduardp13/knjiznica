<template>
  <q-page padding>
    <q-card bordered class="q-pa-md">
      <div class="q-pa-md">
        <h2 class="text-h4 text-center">Traži knjigu</h2>

        <q-input
          filled
          v-model="searchQuery"
          placeholder="Unesite naslov knjige"
          class="q-mb-md"
          label="Naslov knjige"
        />

        <q-btn
          label="Pretraži"
          color="primary"
          icon="search"
          @click="searchBooks"
          class="full-width q-mb-lg"
        />

        <q-list>
          <q-item v-for="book in filteredBooks" :key="book.id">
            <q-item-section>
              <q-item-label>{{ book.title }}</q-item-label>
              <q-item-label caption>{{ book.author }}</q-item-label>
            </q-item-section>
          </q-item>
        </q-list>

        <div
          v-if="filteredBooks.length === 0 && searchPerformed"
          class="text-center text-grey"
        >
          <p>Nema pronađenih knjiga za pretragu: "{{ searchQuery }}"</p>
        </div>

        <!-- Natrag Button -->
        <q-btn
          label="Natrag"
          color="secondary"
          icon="arrow_back"
          class="full-width q-mt-lg"
          @click="goBack"
        />
      </div>
    </q-card>
  </q-page>
</template>

<script>
import { ref } from "vue";
import { useRouter } from "vue-router";
import * as L from "leaflet";

export default {
  name: "TraziKnjiguPage",
  setup() {
    const searchQuery = ref("");
    const searchPerformed = ref(false);

    // Dummy data for books
    const books = ref([
      { id: 1, title: "Harry Potter i Kamen Mudraca", author: "J.K. Rowling" },
      { id: 2, title: "Gospodar Prstenova", author: "J.R.R. Tolkien" },
      { id: 3, title: "Ponos i Predrasude", author: "Jane Austen" },
      { id: 4, title: "Ana Karenjina", author: "Leo Tolstoy" },
    ]);

    const filteredBooks = ref([]);
    const router = useRouter();

    function searchBooks() {
      searchPerformed.value = true;
      filteredBooks.value = books.value.filter((book) =>
        book.title.toLowerCase().includes(searchQuery.value.toLowerCase())
      );
    }

    function goBack() {
      router.back(); // Navigate to the previous page in history
    }

    return {
      searchQuery,
      books,
      filteredBooks,
      searchPerformed,
      searchBooks,
      goBack,
    };
  },
};
</script>

<style scoped>
.full-width {
  width: 100%;
}
</style>
