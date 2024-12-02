<template>
  <q-page padding>
    <q-card dark bordered class="bg-grey-9 my-card">
      <q-card-section>
        <q-img
          src="https://www.rijeka.hr/wp-content/uploads/2023/12/Nova-knji%C5%BEnica-4-901x600.jpg"
        >
          <div class="text-h3 text-weight-bolder absolute-bottom text-center">
            O nama
          </div>
        </q-img>
      </q-card-section>

      <q-card-section class="text-h4 text-justify">
        {{ o_nama }}
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
export default {
  name: "ONamaPage", // Ensures the component name is multi-word
  data() {
    return {
      o_nama:
        "Gradska knjižnica Rija središnja je narodna knjižnica grada Rijeke i matična za narodne i školske knjižnice Primorkso-goranske županije. Ona je informacijsko, obrazovno, kulturno, komunikacijsko i socijalno središte Rijeke i okolice usmjereno prema novom stvaralaštvu, održivom razvoju i kvaliteti razvoja zajednice i čitateljske kulture",
    };
  },
};
</script>

<style lang="sass" scoped>
.my-card
  width: 100%
</style>
