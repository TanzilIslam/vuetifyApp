<template>
  <v-layout>
    <v-flex xs12 sm6 offset-sm3>
      <v-card v-for="(recipe,index) in recipes" :key="index" class="mb-5 p-5">
        <v-img :src="recipe.thumbnail" aspect-ratio="2.75"></v-img>

        <v-card-title primary-title>
          <div>
            <h3 class="headline mb-5">{{ recipe.title}}</h3>
            <div>{{ recipe.previewText }}</div>
          </div>
          <div>
            <h3 class="headline mb-3">{{ recipe.description}}</h3>
          </div>
        </v-card-title>

        <v-card-actions>
          <v-btn flat color="orange">Share</v-btn>
          <v-btn flat color="orange">Explore</v-btn>
        </v-card-actions>
      </v-card>
    </v-flex>
  </v-layout>
</template>

<script>
export default {
  components: {},
  name: "Card",
  data() {
    return {
      recipes: [
        {
          id: "1",
          title: "Sandwitch",
          previewText: "Yammy",
          thumbnail:
            "https://images.wallpaperscraft.com/image/pizza_mushrooms_olives_tomatoes_cheese_95004_300x168.jpg",
          description:
            "It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as opposed to using 'Content here, content here', making it look like readable English. Many desktop publishing packages and web page editors now use Lorem Ipsum as their default model text, and a search for 'lorem ipsum' will uncover many web sites still in their infancy. Various versions have evolved over the years, sometimes by accident, sometimes on purpose (injected humour and the like)."
        },
        {
          id: "2",
          title: "Pizza",
          previewText: "Valo lage",
          thumbnail:
            "https://previews.123rf.com/images/lsantilli/lsantilli1204/lsantilli120400224/13417289-big-sandwich-with-ham-cheese-tomatoes-and-salad-on-toasted-bread.jpg",
          description:
            "It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as opposed to using 'Content here, content here', making it look like readable English. Many desktop publishing packages and web page editors now use Lorem Ipsum as their default model text, and a search for 'lorem ipsum' will uncover many web sites still in their infancy. Various versions have evolved over the years, sometimes by accident, sometimes on purpose (injected humour and the like)."
        }
      ]
    };
  }
};
</script>
<style scoped>
</style>