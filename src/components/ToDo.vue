<template>
  <div class=" m-3">
    <h3>Expense Tracker</h3>
    <CreateExpense @add="addToList" />
    <ExpenseList @del="del" :lists="lists" />
  </div>
</template>

<script>
import CreateExpense from "./CreateExpense.vue";
import ExpenseList from "./ExpenseList.vue";
export default {
  components: {ExpenseList, CreateExpense},
  data() {
    return {
      lists: []
    }
  },
  methods: {
    addToList(data) {
      // this.lists.push(data)
      this.lists = [...this.lists,data]
    },
    del(index){
      console.log(index);
      this.lists = this.lists.filter((list,i) => index !== i)
    }
  },
}
</script>

<style scoped>

</style>