<template>
    <my-catalog :catalog="catalog"></my-catalog>
</template>

<script>
import MyCatalog from "@/components/MyCatalog/MyCatalog";
export default {
  components: {
    'my-catalog': MyCatalog
  },
  data:() => {
      return {
          catalog: [{id:1, name: 'Товар', price: 100, count: 1, category: 1, sum: 100}, 
                    {id:2, name: 'Товар2', price: 200, count: 2, category: 4, sum: 500}]
      }
  }
}
</script>


<style>

</style>
