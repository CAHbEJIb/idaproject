<template>
  <form class="goodsForm" @submit.prevent>
    <h3>Наименование товара</h3>
    <input
      type="text"
      v-model="item.name"
      placeholder="Введите наименование товара"
    />
    <h3>Описание товара</h3>
    <input
      type="text"
      v-model="item.descr"
      placeholder="Введите описание товара"
    />
    <h3>Ссылка на изображение товара</h3>
    <input type="text" v-model="item.image" placeholder="Введите ссылку" />
    <h3>Цена товара</h3>
    <input type="text" v-model="item.price" placeholder="Введите цену" />
    <!-- @click="createItem" удалено из кнопки -->
    <button @click="createItem">Добавить товар</button>
  </form>
</template>
<script>
export default {
  data() {
    return {
      item: {
        name: "",
        descr: "",
        image: "",
        price: "",
      },
    };
  },
  methods: {
    createItem() {
      this.item.id = Date.now();
      this.$emit("createItem", this.item);
      this.item = { name: "", descr: "", image: "", price: "" };
    },
  },
};
</script>
<style scoped>
.goodsform {
  display: inline-block;
}
</style>
