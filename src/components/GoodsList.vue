<template>

    <GoodsItem v-if="goodsItems.length > 0" v-for="item in goodsItems" :item="item" :key="item.id"
        @removeI="$emit('removeI', item)" />

    <h2 v-else>Список товаров пуст</h2>
</template>
<script>
import GoodsItemVue from "./GoodsItem.vue";
import GoodsItem from "./GoodsItem.vue";
export default {
    components: { GoodsItemVue, GoodsItem },
    props: {
        goodsItems: {
            type: Array,
            // Обязательность заполенения всех полей
            required: true,
        },
    },
};
</script>
<style scoped>
</style>
