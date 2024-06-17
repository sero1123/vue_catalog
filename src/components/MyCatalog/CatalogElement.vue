<template>
        <th>{{element.name}}</th>
        <th>{{element.price}}</th>
        <th>{{element.count}}</th>
        <th>{{element.category}}</th>
        <th>{{element.sum}}</th>
</template>

<script>    

export default {
    name: "CatalogElement",
    props: {
        element: Array
    }
}
</script>

<style scoped> 
</style>