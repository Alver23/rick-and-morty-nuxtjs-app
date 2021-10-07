<template>
  <div>
    <article v-for="character in characters" :key="character.id">
      <img :src="character.image" :alt="character.name" />
      <p>{{ character.name }}</p>
    </article>
  </div>
</template>

<script lang="ts">
import Vue from "vue";
import { Context } from "@nuxt/types";

export default Vue.extend({
  async asyncData(ctx: Context): Promise<void | object> {
    const { results } = await ctx.$axios.$get(
      "https://rickandmortyapi.com/api/character"
    );
    return {
      characters: results,
    };
  },
  data: () => ({
    characters: [],
  }),
});
</script>
