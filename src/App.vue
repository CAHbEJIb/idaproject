<template>

	<Header />
	<main class="main">
		<AddGoodsForm class="main__form" @createItem="createItem" />
		<div class="goodsList">
			<GoodsList @removeI="removeItem" :goodsItems="goodsItems" />
		</div>
	</main>

</template>
<script>
import AddGoodsForm from "./components/AddGoodsForm";
import GoodsList from "./components/GoodsList";
import Header from "./components/Header";
export default {
	components: { AddGoodsForm, GoodsList, Header, Header },
	data() {
		return {
			goodsItems: [
				{
					id: 1,
					name: "Наименование товара",
					descr: "Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк",
					image:
						"http://cahbejib23.ru/camera.jpg",
					price: "10 000 руб.",
				},
				{
					id: 2,
					name: "Наименование товара",
					descr: "Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк",
					image:
						"http://cahbejib23.ru/camera.jpg",
					price: "10 000 руб.",
				},
				{
					id: 3,
					name: "Наименование товара",
					descr: "Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк",
					image:
						"http://cahbejib23.ru/camera.jpg",
					price: "10 000 руб.",
				},
				{
					id: 4,
					name: "Наименование товара",
					descr: "Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк",
					image:
						"http://cahbejib23.ru/camera.jpg",
					price: "10 000 руб.",
				},
				{
					id: 5,
					name: "Наименование товара",
					descr: "Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк",
					image:
						"http://cahbejib23.ru/camera.jpg",
					price: "10 000 руб.",
				},
				{
					id: 6,
					name: "Наименование товара",
					descr: "Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк",
					image:
						"http://cahbejib23.ru/camera.jpg",
					price: "10 000 руб.",
				},
				{
					id: 7,
					name: "Наименование товара",
					descr: "Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк",
					image:
						"http://cahbejib23.ru/camera.jpg",
					price: "10 000 руб.",
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
<style lang="scss">
.main {
	display: flex;
	gap: w(16)
}

.goodsList {
	flex: 1;
	display: grid;
	grid-auto-flow: row;
	grid-template-columns: repeat(auto-fit, minmax(w(332), w(332)));
	align-items: start;
	gap: w(16);


}
</style>
