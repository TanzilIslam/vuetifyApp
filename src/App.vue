<template>
  <v-app  app>
    <v-content :aspect-ratio="16/9">
      
      <navbar/>
      <inlineEditor/>
      <orderform/>

      <v-container grid-list-xl>
        <v-layout v-bind="binding">
      <v-flex>
        <v-card  color="primary">
          <instantsearch/>
          </v-card>
      </v-flex>
      <v-flex>
        <v-card  color="secondary">
              <switchableGrid/>
          </v-card>
      </v-flex>
      </v-layout>
      </v-container>
      
  
      </v-content>
  </v-app>
</template>

<script>
import navbar from './components/navbarComponent.vue'
import inlineEditor from './components/inlineEditor.vue'
import orderform from './components/orderform.vue'
import instantsearch from './components/instantsearch.vue'
import switchableGrid from './components/switchableGrid.vue'


export default {
  name: 'App',
  components: {
    navbar,
    inlineEditor,
    orderform,
    instantsearch,
    switchableGrid
  },
  data () {
    return {
      //
    }
  },
  computed: {
      binding () {
        const binding = {}

        if (this.$vuetify.breakpoint.mdAndUp) binding.column = true

        return binding
      }
    }
}
</script>
