<template>
    <div class="goodsList-item__wrapper">
        <div class="goodsList-item__image"><img :src="item.image" /></div>
        <div class="goodsList-item__name">{{ item.name }}</div>
        <div class="goodsList-item__descr">{{ item.descr }}</div>
        <div class="goodsList-item__price">{{ item.price }}</div>
        <button class="goodsList-item__button" @click="$emit('removeI', item)">Удалить</button>
    </div>
</template>
<script>
export default { props: { item: { type: Object, required: true } } };
</script>
<style scoped lang="scss">
.goodsList-item {

    &__name {
        font-size: w(20);
        font-weight: 600;
        line-height: w(25);
        letter-spacing: 0em;
        text-align: left;
        color: $titleColor;
        margin-bottom: w(16);
        padding: 0 w(16);
    }

    &__descr {
        padding: 0 w(16);
        text-align: left;
        font-size: w(16);
        font-weight: 400;
        line-height: w(20);
        letter-spacing: 0em;
        margin-bottom: w(16);

    }

    &__image {
        overflow: hidden;
        max-width: 100px;
        text-align: left;
        min-width: 100%;
        max-height: w(200);
        object-fit: cover;
        object-position: center center;
        margin-bottom: w(16);
    }

    &__price {
        padding: 0 w(16);
        font-size: w(24);
        font-weight: 600;
        line-height: w(30);
        letter-spacing: 0em;
        text-align: left;
        margin-top: auto;
        margin-bottom: w(24);
    }

    &__wrapper {
        position: relative;
        display: flex;
        flex-direction: column;
        min-width: w(332);
        max-width: w(323);
        // min-height: w(423);
        background: $backFormBlock;
        box-shadow: 0px w(20) w(30) rgba(0, 0, 0, 0.04), 0px w(6) w(10) rgba(0, 0, 0, 0.02);
        border-radius: 4px;


        &:hover .goodsList-item__button {
            opacity: 1;
        }
    }

    &__button {
        text-align: left;
        position: absolute;
        top: -10px;
        right: -10px;
        opacity: 0;
        cursor: pointer;
    }
}
</style>
