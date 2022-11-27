<template>
  <form @submit.prevent="add" action="">
    <div class="row mt-3">
      <div class="col-4">
        <div class="form-floating ">
          <input type="text"  v-model="why" class="form-control" required id="floatingInput" placeholder="name@example.com">
          <label for="floatingInput">ဘာသုံးလိုက်တာလဲ ? </label>
        </div>
      </div>
      <div class="col-4">
        <div class="form-floating ">
          <input type="number" v-model.number="amount" class="form-control" required id="floatingInput" placeholder="name@example.com">
          <label for="floatingInput"> ဘယ်လောက်သုံးလိုက်တာလဲ ? </label>
        </div>
      </div>
      <div class="col-4">
        <button class=" btn btn-lg btn-primary h-100">စာရင်သွင်း</button>
      </div>
    </div>
  </form>
</template>

<script>
export default {
  data() {
    return {
      why: null,
      amount: null,
    }
  },
  methods: {
    add() {
      const data = {
        why:this.why,
        amount: this.amount
      };
      console.log(data)
      this.$emit('add',data);
      this.why =null;
      this.amount = null;
    }
  },
}
</script>

<style scoped>

</style>