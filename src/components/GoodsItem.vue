<template>
  <div class="goodsList-item__wrapper">
    <div class="goodsList-item__name">{{ item.name }}</div>
    <div class="goodsList-item__descr">{{ item.descr }}</div>
    <img class="goodsList-item__image" :src="item.image" />
    <div class="goodsList-item__price">{{ item.price }}</div>
    <button @click="$emit('removeI', item)">Удалить</button>
  </div>
</template>
<script>
export default { props: { item: { type: Object, required: true } } };
</script>
<style scoped>
.goodsList-item__wrapper {
  display: inline-block;
  border: 1px solid black;
}
.goodsList-item__image {
  max-width: 100px;
}
</style>
