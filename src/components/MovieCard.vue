<template>
  <v-card>
    <v-img class="white--text align-end" height="200px" src="https://cdn.vuetifyjs.com/images/cards/docks.jpg" />
    <v-card-title>Movie Name</v-card-title>
    <v-card-subtitle class="pb-0">
      <v-chip class="ma-2" color="green darken-3">
        Primary
      </v-chip></v-card-subtitle
    >

    <v-card-text class="text--primary">
      <div>Whitehaven Beach</div>

      <div>Whitsunday Island, Whitsunday Islands</div>
    </v-card-text>

    <v-card-actions>
      <v-btn color="orange" text>
        Share
      </v-btn>

      <v-btn color="orange" text>
        Explore
      </v-btn>
    </v-card-actions>
  </v-card>
</template>

<script>
export default {
  name: 'MovieCard',
}
</script>
