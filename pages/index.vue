<template>
  <div>
    <div v-for="(character, index) in characters" v-bind:key="index">
      <character-card :data="character" :id="index + 1" />
    </div>
  </div>
</template>

<script>
export default {
  async asyncData({ $axios }) {
    const endpoint = '/people';
    const { results: characters } = await $axios.$get(endpoint);
    return { characters }
  }
}
</script>