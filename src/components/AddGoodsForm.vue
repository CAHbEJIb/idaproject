<template>
    <form class="goodsForm" @submit.prevent>
        <h2 class="goodsForm__title">Добавление товара</h2>
        <h3 class="goodsForm__subtitle">Наименование товара</h3>
        <input class="goodsForm__input" type="text" v-model="item.name" placeholder="Введите наименование товара" />
        <h3 class="goodsForm__subtitle">Описание товара</h3>
        <input class="goodsForm__input" type="text" v-model="item.descr" placeholder="Введите описание товара" />
        <h3 class="goodsForm__subtitle">Ссылка на изображение товара</h3>
        <input class="goodsForm__input" type="text" v-model="item.image" placeholder="Введите ссылку" />
        <h3 class="goodsForm__subtitle">Цена товара</h3>
        <input class="goodsForm__input" type="text" v-model="item.price" placeholder="Введите цену" />
        <!--  удалено из кнопки -->
        <button :disabled="!this.item.name || !this.item.image || !this.item.price" class="goodsForm__button"
            @click="createItem">
            Добавить товар
        </button>


    </form>
</template>
<script>

export default {
    data() {
        return {
            show: false,
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
            if (this.item.name && this.item.image && this.item.price) {
                if (this.item.price) {
                    this.item.price = this.item.price
                        .toString()
                        .replace(/\B(?=(\d{3})+(?!\d))/g, "\xa0");
                }

                this.$emit("createItem", this.item);
                this.item = { name: "", descr: "", image: "", price: "" };
            }
            else {
                document
                    .querySelector(".goodsform__button")
                    .setAttribute("disabled", true);
            }
        },

    },
};
</script>
<style scoped lang="scss">
.goodsForm {
    position: fixed;
    display: inline-block;

    left: w(32);


    &__button {
        font-family: 'Inter', sans-serif;
        width: 100%;
    }

    &__title {}

    &__subtitle {}

    &__input {}


}
</style>
