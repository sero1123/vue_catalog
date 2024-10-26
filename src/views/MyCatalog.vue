<template>
    <div class="catalog">
      <my-catalog :catalog="catalog"
                  @priceFrom="priceFrom"
                  @priceTo="priceTo"
                  @category="category"
                  @countFrom="countFrom"
                  @countTo="countTo"></my-catalog>
    </div>
</template>

<script>
import MyCatalog from "@/components/MyCatalog";
export default {
  components: {
    'my-catalog': MyCatalog
  },
  data:() => {
      return {
          catalog: [{id:1, name: 'Товар', price: 100, count: 1, category: 1, sum: 100, image: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTidJg8UJ4145gajC0mJa6zi83nKnTeKj6Tqw&s'}, 
                    {id:2, name: 'Товар2', price: 200, count: 2, category: 4, sum: 500, image: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTidJg8UJ4145gajC0mJa6zi83nKnTeKj6Tqw&s'},
                    {id:3, name: 'Товар3', price: 300, count: 3, category: 3, sum: 900, image: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTidJg8UJ4145gajC0mJa6zi83nKnTeKj6Tqw&s'},
                    {id:4, name: 'Товар4', price: 400, count: 4, category: 2, sum: 1600, image: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTidJg8UJ4145gajC0mJa6zi83nKnTeKj6Tqw&s'},
                    {id:5, name: 'Товар5', price: 500, count: 5, category: 5, sum: 2500, image: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTidJg8UJ4145gajC0mJa6zi83nKnTeKj6Tqw&s'},
                  ],
          priceFromValue: 0,
          priceToValue: 0,
          countFromValue: 0,
          countToValue: 0,
          categoryValue: 0
      }
  },
  methods: {
      priceFrom(value) {
          this.priceFromValue = value
      },
      priceTo(value) {
          this.priceToValue = value
      },
      category(value) {
          this.categoryValue = value
      },
      countFrom(value) {
          this.countFromValue = value
      },
      countTo(value) {
          this.countToValue = value
      },
      filterCatalog() {
          
      }
  }
}
</script>


<style>
.catalog {
    padding: 20px;
    font-family: "Arial";
    font-size: 14px;
    color: #2c3e50;
    margin-top: 60px;
    background-color: lightblue;
    min-height: 100vh;
    display: flex;
    flex-direction: column;
}
</style>
