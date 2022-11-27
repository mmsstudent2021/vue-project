<template>
  <div class="m-3">
    <button @click="showBox = false" class=" btn btn-primary">
      Hide
    </button>

    <div v-if="showBox" class=" border border-primary mt-3 p-3 rounded">
      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Accusantium assumenda atque debitis, eaque error et exercitationem id illo iure maxime minus nesciunt quibusdam sed temporibus voluptas. A amet esse sit.
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      showBox: true
    }
  },
}
</script>

<style scoped>

</style>