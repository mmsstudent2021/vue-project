<template>
  <div class=" p-3">
    <h1>F&Q Component</h1>
    <div class=" border border-primary p-3 rounded">
      <FaqItem @open="open" :list-detail="list" v-for="(list,index) in lists" />
    </div>
  </div>
</template>

<script>
import FaqItem from "./FaqItem.vue";
export default {
  components: {FaqItem},
  methods: {
    open(status,id) {
      console.log(status,id)
      this.lists = this.lists.map(list => {
        if(list.id === id){
          list.isOpen = status
        }else{
          list.isOpen = false
        }
        return list;
      })
    }
  },
  data() {
    return {
      lists: [
        {
          id : 1,
          isOpen : true,
          title : "This is title 1",
          body : "This is the first item's accordion body. It is shown by default, until the collapse plugin adds the appropriate classes that we use to style each element. These classes control the overall appearance, as well as the showing and hiding via CSS transitions. You can modify any of this with custom CSS or overriding our default variables. It's also worth noting that just about any HTML can go within the .accordion-body, though the transition does limit overflow."
        },
        {
          id : 2,
          isOpen : false,
          title : "This is title 2",
          body : "This is the first item's accordion body. It is shown by default, until the collapse plugin adds the appropriate classes that we use to style each element. These classes control the overall appearance, as well as the showing and hiding via CSS transitions. You can modify any of this with custom CSS or overriding our default variables. It's also worth noting that just about any HTML can go within the .accordion-body, though the transition does limit overflow."
        },
        {
          id : 3,
          isOpen : false,

          title : "This is title 3",
          body : "This is the first item's accordion body. It is shown by default, until the collapse plugin adds the appropriate classes that we use to style each element. These classes control the overall appearance, as well as the showing and hiding via CSS transitions. You can modify any of this with custom CSS or overriding our default variables. It's also worth noting that just about any HTML can go within the .accordion-body, though the transition does limit overflow."
        }
      ]
    }
  },
}
</script>

<style scoped>

</style>