<template>
  <div>
    <table class=" table table-bordered mt-3">
      <thead>
      <tr>
        <th>Control</th>
        <th>#</th>
        <th class="text-center">Why</th>
        <th class="text-end">Amount</th>
      </tr>
      </thead>
      <tbody>
      <tr v-if="lists.length === 0">
        <td colspan="4" class="text-center">There is no expense</td>
      </tr>
      <tr v-for="(list,index) in lists" :key="index">
        <td>
          <button @click="del(index)" class=" btn btn-sm btn-danger">
            <i class=" bi bi-trash3"></i>
          </button>
        </td>
        <td>{{ index+1 }}</td>
        <td class="text-center">{{ list.why }}</td>
        <td class=" text-end">{{ list.amount }}</td>
      </tr>
      </tbody>
      <tfoot>
      <tr>
        <td colspan="3" class=" text-center">Total</td>
        <td class="text-end">{{ totalExpense }}</td>
      </tr>
      </tfoot>
    </table>
  </div>
</template>

<script>
export default {
  props: {
    lists: {
      type: Array
    },
  },
  computed: {
    totalExpense() {
      return this.lists.reduce((pv,cv)=>pv+cv.amount,0)
    }
  },
  methods: {
    del(index) {
      if(confirm('Are U sure to delete?')){
        this.$emit("del",index)
      }
    }
  },
}
</script>

<style scoped>

</style>