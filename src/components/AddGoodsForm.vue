<template>
    <form class="goodsForm" @submit.prevent>

        <div class="goodsForm__block">
            <h3 class="goodsForm__subtitle goodsForm__needs">Наименование товара</h3>
            <input required class="goodsForm__input goodsForm__input--name" type="text" v-model="item.name"
                placeholder="Введите наименование товара" />
            <p class="goodsForm__input--valid">Поле является обязательным</p>
            <h3 class="goodsForm__subtitle">Описание товара</h3>
            <textarea class="goodsForm__input goodsForm__input--descr" type="text" v-model="item.descr"
                placeholder="Введите описание товара" />
            <h3 class="goodsForm__subtitle goodsForm__needs">Ссылка на изображение товара</h3>
            <input required class="goodsForm__input goodsForm__input--iamge" type="text" v-model="item.image"
                placeholder="Введите ссылку" />
            <p class="goodsForm__input--valid">Поле является обязательным</p>
            <h3 class="goodsForm__subtitle goodsForm__needs goodsForm__price">Цена товара</h3>
            <input required class="goodsForm__input goodsForm__input--price" type="text" v-model="item.price"
                placeholder="Введите цену" />
            <p class="goodsForm__input--valid">Поле является обязательным</p>
            <button :disabled="!this.item.name || !this.item.image || !this.item.price" class="goodsForm__button"
                @click="createItem">
                Добавить товар
            </button>
        </div>
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
                    this.item.price = this.item.price + ' руб.'
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
    max-width: w(332);
    display: inline-block;

    &__block {
        background: $backFormBlock;
        box-shadow: 0px w(20) w(30) rgba(0, 0, 0, 0.04), 0px w(6) w(10) rgba(0, 0, 0, 0.02);
        border-radius: w(4);
        padding: w(24);
    }

    &__subtitle {
        font-size: w(10);
        line-height: w(13);
        font-weight: normal;
        letter-spacing: -0.02em;
        margin-bottom: w(4);
        color: $subTitleColor;
    }

    &__input {
        font-weight: normal;
        background: $backFormBlock;
        box-shadow: 0px w(2) w(5) rgba(0, 0, 0, 0.1);
        border-radius: w(4);
        width: 100%;
        border: 0;
        font-size: w(12);
        line-height: w(15);
        padding: w(11) w(16);
        margin-bottom: w(6);

        &:focus:invalid {
            outline: 1px solid $needsBack;
        }

        &:focus:invalid+.goodsForm__input--valid {
            opacity: 1;

            font-size: w(8);
            font-weight: 400;
            line-height: w(10);
            letter-spacing: -0.02em;
            color: $needsBack;
        }

        &--name,
        &--image,
        &--price {
            min-height: w(36);
            max-height: w(36);
        }



        &--descr {
            min-height: w(108);
            resize: none;
        }

        &--valid {
            opacity: 0;
            font-size: w(8);
            font-weight: 400;
            line-height: w(10);
            letter-spacing: -0.02em;
            color: $needsBack;

        }

        &::placeholder {
            font-weight: normal;
            font-size: w(12);
            line-height: w(15);
            letter-spacing: 0em;
            color: $placeholderColor;
        }
    }

    &__button {
        font-family: 'Inter', sans-serif;
        width: 100%;
        background: $buttonBack;
        border-radius: w(10);
        font-size: w(12);
        font-weight: 600;
        line-height: w(15);
        letter-spacing: -0.02em;
        text-align: center;
        padding: w(10) w(95);
        margin-top: w(24);
        color: $main;
        background: $buttonBack;
        white-space: nowrap;
        cursor: pointer;

        &:active {
            transform: translate(w(2), w(2));
        }

        &:disabled {
            cursor: inherit;
            background: $buttonDisBack;
            color: $placeholderColor;
        }

    }

    &__needs {
        display: inline-block;
        white-space: nowrap;
        position: relative;

        &:after {
            content: '';
            position: absolute;
            top: 0;
            right: w(-6);
            width: w(4);
            height: w(4);
            border-radius: 50%;
            background: $needsBack;
        }
    }
}
</style>
