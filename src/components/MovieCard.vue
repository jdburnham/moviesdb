<template>
  <v-card>
    <v-img class="white--text align-end" contain :src="`${imageURL}${movie.poster_path}`" />
    <v-card-title>{{ movie.title }}</v-card-title>
    <v-card-subtitle class="pb-0">
      <v-chip v-for="genre in movie.genre_ids" :key="genre" class="ma-2 green--text text--darken-3" color="green lighten-4" x-small>
        {{ genres.find(g => g.id === genre).name }}
      </v-chip>
    </v-card-subtitle>

    <v-card-text class="text--primary">{{ movie.overview }}</v-card-text>

    <v-card-actions>
      <v-btn color="red darken-3" text>Love It</v-btn>
      <v-spacer />
      <v-btn color="orange" text>Watchlist</v-btn>
    </v-card-actions>
  </v-card>
</template>

<script>
export default {
  name: 'MovieCard',
  props: {
    movie: {
      type: Object,
      default: () => {},
    },
    imageURL: {
      type: String,
      default: '',
    },
  },
  data() {
    return {
      genres: [],
    }
  },
  created() {
    this.getGenres()
  },
  methods: {
    async getGenres() {
      const genres = await this.$axios('genre/movie/list')
      this.genres = genres.data?.genres
    },
  },
}
</script>
