<template>
  <q-page padding>
    <q-card bordered class="q-pa-md">
      <q-toolbar-title>POPIS KNJIGA</q-toolbar-title>

      <q-card-section class="text-h6 text-justify">
        Ovdje možeš pogledati popis knjiga.
      </q-card-section>

      <!-- Quasar Table displaying dummy books data -->
      <q-table
        :rows="books"
        :columns="columns"
        row-key="id"
        :filter="filter"
        :rows-per-page-options="[5, 10, 15]"
        :pagination="pagination"
      >
        <template v-slot:top-right>
          <q-input
            v-model="filter"
            debounce="300"
            label="Pretraži knjige"
            filled
            square
            dense
          />
        </template>
      </q-table>

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
export default {
  name: "PopisKnjigaPage",
  data() {
    return {
      // Dummy podaci
      books: [
        {
          id: 1,
          title: "Don Quijote",
          author: "Miguel de Cervantes",
          description: "1605. (1. dio), 1615. (2. dio) - Španjolska",
          image: "https://via.placeholder.com/150",
          status: 10, // Broj dostupnih kopija
        },
        {
          id: 2,
          title: "Starac i more",
          author: "Ernest Hemingway",
          description: "1952. - SAD",
          image: "https://via.placeholder.com/150",
          status: 5,
        },
        {
          id: 3,
          title: "Put oko svijeta u osamdeset dana",
          author: "Jules Verne",
          description: "1873. - Francuska",
          image: "https://via.placeholder.com/150",
          status: 8,
        },
        {
          id: 4,
          title: "Životinjska farma",
          author: "George Orwell",
          description: "1945. - Velika britanija",
          image: "https://via.placeholder.com/150",
          status: 9,
        },
        {
          id: 5,
          title: "Otac Goriot",
          author: "Honore de Balzac",
          description: "1835. - Francuska",
          image: "https://via.placeholder.com/150",
          status: 3,
        },
      ],

      columns: [
        { name: "title", label: "Naslov", align: "left", field: "title" },
        { name: "author", label: "Autor", align: "left", field: "author" },
        {
          name: "description",
          label: "Opis",
          align: "left",
          field: "description",
        },
        { name: "status", label: "Stanje", align: "center", field: "status" },
        {
          name: "image",
          label: "Slika",
          align: "center",
          field: "image",
          // Custom slot to render image
          required: true,
          sortable: false,
        },
      ],
      filter: "", // search string
      pagination: {
        page: 1,
        rowsPerPage: 5,
      },
    };
  },
};
</script>

<style scoped>
/* Add any custom styles for your table or page */
</style>
