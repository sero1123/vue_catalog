<template>
    <div class="app">
      <my-catalog :catalog="genProduct"></my-catalog>
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
          catalog: [{id:1, name: 'Товар', price: 100, count: 1, contacts: 9192325987, sum: 100, image: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTidJg8UJ4145gajC0mJa6zi83nKnTeKj6Tqw&s'}, 
                    {id:2, name: 'Товар2', price: 200, count: 2, contacts: 9192325987, sum: 500, image: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTidJg8UJ4145gajC0mJa6zi83nKnTeKj6Tqw&s'},
                    {id:3, name: 'Товар3', price: 400, count: 3, contacts: 9192325987, sum: 200, image: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTidJg8UJ4145gajC0mJa6zi83nKnTeKj6Tqw&s'},
                    {id:4, name: 'Товар4', price: 123, count: 4, contacts: 9192325987, sum: 5000, image: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTidJg8UJ4145gajC0mJa6zi83nKnTeKj6Tqw&s'},
                    {id:5, name: 'Товар5', price: 500, count: 5, contacts: 9192325987, sum: 2500, image: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTidJg8UJ4145gajC0mJa6zi83nKnTeKj6Tqw&s'},
                  ],      }
  }, methods: {

  }, computed: {
    genProduct () {
          const generateProducts = (count) => {
          return Array.from({ length: count }, (_, index) => {
            const id = index + 1;
            const name = `Товар ${id}`;
            const price = Math.floor(Math.random() * 1000);
            const count = Math.floor(Math.random() * 10) + 1;
            const contacts = Math.floor(Math.random() * 10000000000);
            const sum = price * count;
            const image = 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTidJg8UJ4145gajC0mJa6zi83nKnTeKj6Tqw&s';
        
            return { id, name, price, count, contacts, sum, image };
          });
        };
        
        const products = generateProducts(101);
        console.log(products);
        return products
      }
  }
}
</script>


<style>
.app {
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
