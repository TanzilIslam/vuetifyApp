<template>
  <v-app app>
    <v-content :aspect-ratio="16/9">
      <v-container grid-list-xl>
        <v-layout v-bind="binding">
          <navbar />
          <inlineEditor />
          <orderform />
          <instantsearch />
          <switchableGrid />
          <Card/>
        </v-layout>
      </v-container>
    </v-content>
  </v-app>
</template>

<script>
import navbar from "./components/navbarComponent.vue";
import inlineEditor from "./components/inlineEditor.vue";
import orderform from "./components/orderform.vue";
import instantsearch from "./components/instantsearch.vue";
import switchableGrid from "./components/switchableGrid.vue";
import Card from "./components/Card.vue";

export default {
  name: "App",
  components: {
    navbar,
    inlineEditor,
    orderform,
    instantsearch,
    switchableGrid,
    Card
  },
  data() {
    return {
      //
    };
  },
  computed: {
    binding() {
      const binding = {};

      if (this.$vuetify.breakpoint.mdAndUp) binding.column = true;

      return binding;
    }
  }
};
</script>
