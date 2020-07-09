<template>
  <div class="card">
    <div class="card-content">
      <h4 v-if="!single"><b><nuxt-link :to="`characters/${id}`">{{ data.name }}</nuxt-link></b></h4>
      <h4 v-else>
        <b>{{ data.name }}</b>
        <p>
          <nuxt-link to="/">Back</nuxt-link>
        </p>
      </h4>
      <p>{{ data.birth_year }}</p>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    data: {
      type: Object,
      default() {
        return {}
      }
    },
    id: {
      type: Number,
      default: 0
    },
    single: {
      type: Boolean,
      default: false
    }
  }
}
</script>
<style scoped>
.card {
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
  transition: 0.3s;
  margin: 10px;
}

.card:hover {
  box-shadow: 0 8px 16px 0 rgba(0, 0, 0, 0.2);
}

.card-content {
  padding: 2px 16px;
}
</style>