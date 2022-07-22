<template>
  <div>
    <h2>Добавление товара</h2>
    <form class="goodsForm" @submit.prevent>
      <h3>Наименование товара</h3>
      <input
        type="text"
        v-bind:value="name"
        @input="name = $event.target.value"
        placeholder="Введите наименование товара"
      />
      <h3>Описание товара</h3>
      <input
        type="text"
        v-bind:value="descr"
        @input="descr = $event.target.value"
        placeholder="Введите описание товара"
      />
      <h3>Ссылка на изображение товара</h3>
      <input
        type="text"
        v-bind:value="image"
        @input="image = $event.target.value"
        placeholder="Введите ссылку"
      />
      <h3>Цена товара</h3>
      <input
        type="text"
        v-bind:value="price"
        @input="price = $event.target.value"
        placeholder="Введите цену"
      />
      <button @click="createItem">Добавить товар</button>
    </form>
    <div class="goodsList">
      <div class="goodsList-item__wrapper" v-for="item in goodsItems">
        <div class="goodsList-item__name">{{ item.name }}</div>
        <div class="goodsList-item__descr">{{ item.descr }}</div>
        <img class="goodsList-item__image" :src="item.image" />
        <div class="goodsList-item__price">{{ item.price }}</div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
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
      name: "",
      descr: "",
      image: "",
      price: "",
    };
  },
  methods: {
    createItem() {
      const newItem = {
        id: Date.now(),
        name: this.name,
        descr: this.descr,
        image: this.image,
        price: this.price,
      };
      this.goodsItems.push(newItem);
      this.name = "";
      this.descr = "";
      this.image = "";
      this.price = "";
    },
  },
};
</script>
<style>
.goodsList-item__image {
  max-width: 100px;
}
.goodsList-item__wrapper {
  display: inline-block;
  border: 1px solid black;
}
.goodsList {
  display: inline-block;
}
.goodsform {
  display: inline-block;
}
</style>
