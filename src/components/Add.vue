<template>
  <div>
    <v-card class="mx-auto" max-width="600">
      <v-card-title>
        <h3>Ajouter un nouvel appartement</h3>
      </v-card-title>
      <v-card-text>
        <form @submit.prevent="ajouterAppartement">
          <div>
            <v-text-field label="Nombre de chambres" v-model="nouvelAppartement.nbRooms" type="number" id="nbRooms" required />
          </div>
          <div>
            <v-text-field label="Surface (m²)" v-model="nouvelAppartement.surface" type="number" id="surface" required />
          </div>
          <div>
            <v-text-field label="Nombre de fenêtres" v-model="nouvelAppartement.nbWindows" type="number" id="nbWindows" required />
          </div>
          <div>
            <v-text-field label="Prix" v-model="nouvelAppartement.price" type="number" id="price" required />
          </div>
          <div>
            <v-text-field label="Année de construction" v-model="nouvelAppartement.annee" type="number" id="annee" required />
          </div>
          <div>
            <v-checkbox v-model="nouvelAppartement.balcon" label="Balcon" id="balcon" />
          </div>
          <div>
            <v-checkbox v-model="nouvelAppartement.garage" label="Garage" id="garage" />
          </div>
          <div>
            <v-text-field label="Note (1 à 5)" v-model="nouvelAppartement.note" type="number" min="1" max="5" id="note" required />
          </div>
          <div>
            <v-select 
              v-model="nouvelAppartement.price_category" 
              :items="['low', 'normal', 'high', 'scam']" 
              label="Catégorie de prix" 
              id="price_category" 
              required
            />
          </div>
          <v-btn type="submit">Ajouter l'appartement</v-btn>
        </form>
      </v-card-text>
    </v-card>
  </div>
</template>

<script>
import { defineComponent, reactive } from 'vue';

export default defineComponent({
  name: "AjoutAppartement",
  emits: ['appartement-ajoute'],
  setup(props, { emit }) {
    const nouvelAppartement = reactive({
      nbRooms: 4,
      surface: 20,
      nbWindows: 3,
      price: 100000,
      annee: 2024,
      balcon: false,
      garage: false,
      note: 1,
      price_category: 'low'
    });

    const ajouterAppartement = () => {
      // Générer un ID unique pour le nouvel appartement
      const nouvelId = Date.now();
      const appartementComplet = { ...nouvelAppartement, id: nouvelId };
      emit('appartement-ajoute', appartementComplet);

      // Réinitialiser le formulaire
      nouvelAppartement.nbRooms = 4;
      nouvelAppartement.surface = 20;
      nouvelAppartement.nbWindows = 3;
      nouvelAppartement.price = 100000;
      nouvelAppartement.annee = 2024;
      nouvelAppartement.balcon = false;
      nouvelAppartement.garage = false;
      nouvelAppartement.note = 1;
      nouvelAppartement.price_category = 'low';
    };

    return { nouvelAppartement, ajouterAppartement };
  }
});
</script>
