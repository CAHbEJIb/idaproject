<template>
  <div>
    <h2>Добавление товара</h2>
    <AddGoodsForm @createItem="createItem" />
    <div class="GoodsList">
      <GoodsList @removeI="removeItem" :goodsItems="goodsItems" />
    </div>
  </div>
</template>
<script>
import AddGoodsForm from "./components/AddGoodsForm";
import GoodsList from "./components/GoodsList";
export default {
  components: { AddGoodsForm, GoodsList },
  data() {
    return {
      goodsItems: [
        {
          id: 1,
          name: "123",
          descr: "1231111",
          image:
            "https://www.peoples.ru/art/cinema/actor/sasha_grey/grey_201105131531394.jpg",
          price: "1000руб",
        },
        {
          id: 2,
          name: "1231",
          descr: "1231111",
          image:
            "https://www.peoples.ru/art/cinema/actor/sasha_grey/grey_201105131531394.jpg",
          price: "1000руб",
        },
        {
          id: 3,
          name: "121",
          descr: "1231111",
          image:
            "https://www.peoples.ru/art/cinema/actor/sasha_grey/grey_201105131531394.jpg",
          price: "1000руб",
        },
      ],
    };
  },
  methods: {
    createItem(item) {
      this.goodsItems.push(item);
    },
    removeItem(item) {
      this.goodsItems = this.goodsItems.filter((i) => i.id !== item.id);
    },
  },
};
</script>
<style>
.goodsList {
  display: inline-block;
}
</style>
