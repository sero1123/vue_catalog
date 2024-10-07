<template>
    <div>
        <h1>My Catalog</h1>

        <catalog-menu @sortedAndFilter="sortedAndFilterMethod">

        </catalog-menu>      
        <table class="table table-striped">
            <tr>
                <th>название</th>
                <th>цена</th>
                <th>количество</th>
                <th>Контакты продавца</th>
                <th>сумма</th>
                <th>фото</th>
            </tr>
            <tr v-for="item in sortedAndFilteredCatalog" :key="item.id">
                <catalog-element :element="item"></catalog-element>
            </tr>
        </table>
    </div>
</template>

<script>
import CatalogElement from "@/components/CatalogElement";
import CatalogMenu from "@/components/CatalogMenu";
export default {
    name: "MyCatalog",
    components: {
        'catalog-element': CatalogElement,
        'catalog-menu': CatalogMenu,
    },
    data() {
        return {
            sortedAndFilter: {
                priceFrom: null,
                priceTo: Infinity,
                countFrom: null,
                countTo: Infinity,
                contacts: '',
                sorted: 'up',
                sortedType: 'id'
            }
        }
    },
    props: {
        catalog: Array
    },
    methods: {
        sortedAndFilterMethod(value) {
            this.sortedAndFilter = value
        }
    }, computed: {
        filteredCatalog() {
          return [...this.catalog].filter(item => {
              let minPrice = this.sortedAndFilter.priceFrom == '' || this.sortedAndFilter.priceFrom == null ? 0 : this.sortedAndFilter.priceFrom
              let maxPrice = this.sortedAndFilter.priceTo == '' || this.sortedAndFilter.priceTo == null ? Infinity : this.sortedAndFilter.priceTo
              let minCount = this.sortedAndFilter.countFrom == '' || this.sortedAndFilter.countFrom == null ? 0 : this.sortedAndFilter.countFrom
              let maxCount = this.sortedAndFilter.countTo == '' || this.sortedAndFilter.countTo == null ? Infinity : this.sortedAndFilter.countTo
              if (item.price >= minPrice && item.price <= maxPrice && item.count >= minCount && item.count <= maxCount) {
                  if (this.sortedAndFilter.contacts != null && this.sortedAndFilter.contacts != '') {
                      if (item.contacts == this.contacts) {
                          return item
                      }
                  }else{
                      return item
                  }             
            }
          })
        },
        sortedAndFilteredCatalog() {
            return [...this.filteredCatalog].sort((item1, item2) => {
                if (this.sortedAndFilter.sorted == 'up') {
                    return item1[this.sortedAndFilter.sortedType] > item2[this.sortedAndFilter.sortedType] ? 1 : -1
                } else {
                    return item1[this.sortedAndFilter.sortedType] < item2[this.sortedAndFilter.sortedType] ? 1 : -1
                }
            })
        }
    }
}
</script>

<style scoped>
.table, td, th {
    border-collapse: collapse;
    border-spacing: 0;
    border: 4px solid black;
    font-size: 18px;
}
</style>
