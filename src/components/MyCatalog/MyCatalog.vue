<template>
    <div>
        <h1>My Catalog</h1>
        <tr>
            <th>название</th>
            <th>цена</th>
            <th>количество</th>
            <th>категория</th>
            <th>сумма</th>
        </tr>
        <tr v-for="item in catalog" :key="item.id">
            <catalog-element :element="item"></catalog-element>
        </tr>
    </div>
</template>

<script>
import CatalogElement from "@/components/MyCatalog/CatalogElement";
export default {
    name: "MyCatalog",
    components: {
        'catalog-element': CatalogElement,
    },
    props: {
        catalog: Array
    }
}
</script>

<style scoped>


</style>
