<template>
        <th>{{element.name}}</th>
        <th>{{element.price}}</th>
        <th>{{element.count}}</th>
        <th>{{element.category}}</th>
        <th>{{element.sum}}</th>
        <th><img :src="element.image"></th>
</template>

<script>    

export default {
    name: "CatalogElement",
    props: {
        element: Object
    }
}
</script>

<style scoped> 
</style>