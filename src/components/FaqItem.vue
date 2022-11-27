<template>
  <div class="">
    <h3 @click="listOpen" :class="{'bg-primary text-white':listDetail.isOpen}" class=" border border-primary text-primary p-3 rounded">{{ listDetail.title }}</h3>
    <div :class="{'d-none':!listDetail.isOpen}" class="my-3">
      {{ listDetail.body }}
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      // isOpen: this.listDetail.isOpen
    }
  },
  methods: {
    listOpen() {
      // this.isOpen = !this.isOpen
      this.$emit("open",!this.listDetail.isOpen,this.listDetail.id)
    }
  },
  props: ['listDetail'],
}
</script>

<style scoped>

</style>