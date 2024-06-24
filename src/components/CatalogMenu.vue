<template>
    <div class="catalog-menu">
        <my-input :MyPlaceholder="this.priceFromText"
                    v-model = "this.priceFrom"
                    :typeInput = "'number'"
                    :minInput = "0"
                    
        ></my-input>
        <my-input :MyPlaceholder="this.priceToText"
                    v-model = "this.priceTo"
                    :typeInput = "'number'"
                    :minInput = "0"
                    
        ></my-input>
        <my-input :MyPlaceholder="this.countFromText"
                    v-model = "this.countFrom"
                    :typeInput = "'number'"
                    :minInput = "0"
        
        ></my-input>
        <my-input :MyPlaceholder="this.countToText"
                    v-model = "this.countTo"
                    :typeInput = "'number'"
                    :minInput = "0"

        ></my-input>
        <my-input :MyPlaceholder="this.categoryText"
                    v-model = "this.category"
                    :typeInput = "'text'"
                    :minInput = "0"
        
        ></my-input>
    </div>
</template>

<script>
import MyInput from "@/shared/MyInput";
export default {
    name: "CatalogMenu",
    components: {
        'my-input': MyInput,
    },
    data:() => {
        return {
            priceFrom: 0,
            priceTo: 0,
            countFrom: 0,
            countTo: 0,
            category: '',
            priceFromText: 'Цена от',
            priceToText: 'Цена до',
            countFromText: "Количество от",
            countToText: "Количество до",
            categoryText: "Категория"
        }
    },
    watch: {
        priceFrom() {
            this.$emit('priceFrom', this.priceFrom)
        },
        priceTo() {
            this.$emit('priceTo', this.priceTo)
        },
        countFrom() {
            this.$emit('countFrom', this.countFrom)
        },
        countTo() {
            this.$emit('countTo', this.countTo)
        },
        category() {
            this.$emit('category', this.category)
        }
    }
}
</script>

<style scoped>
.catalog-menu {
    display: flex;
    border: 1px solid black;
    flex-wrap: wrap;

}

</style>