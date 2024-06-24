<template>
    <div>
        <h1>My Catalog</h1>

        <catalog-menu @priceFrom="priceFrom"
                    @priceTo="priceTo" 
                    @category="category"
                    @countFrom="countFrom" 
                    @countTo="countTo">

        </catalog-menu>      
        <table class="table table-striped">
            <tr>
                <th>название</th>
                <th>цена</th>
                <th>количество</th>
                <th>категория</th>
                <th>сумма</th>
                <th>фото</th>
            </tr>
            <tr v-for="item in catalog" :key="item.id">
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
    props: {
        catalog: Array
    },
    methods: {
        priceFrom(value) {
            this.$emit('priceFrom', value)
        },
        priceTo(value) {
            this.$emit('priceTo', value)
        },
        category(value) {
            this.$emit('category', value)
        },
        countFrom(value) {
            this.$emit('countFrom', value)
        },
        countTo(value) {
            this.$emit('countTo', value)
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
