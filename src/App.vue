<template>

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
					price: "10 000 руб.",
				},
				{
					id: 2,
					name: "1231",
					descr: "1231111",
					image:
						"https://www.peoples.ru/art/cinema/actor/sasha_grey/grey_201105131531394.jpg",
					price: "10 000 руб.",
				},
				{
					id: 3,
					name: "121",
					descr: "1231111",
					image:
						"https://www.peoples.ru/art/cinema/actor/sasha_grey/grey_201105131531394.jpg",
					price: "10 000 руб.",
				},
				{
					id: 3,
					name: "121",
					descr: "1231111",
					image:
						"https://www.peoples.ru/art/cinema/actor/sasha_grey/grey_201105131531394.jpg",
					price: "10 000 руб.",
				},
				{
					id: 3,
					name: "121",
					descr: "1231111",
					image:
						"https://www.peoples.ru/art/cinema/actor/sasha_grey/grey_201105131531394.jpg",
					price: "10 000 руб.",
				},
				{
					id: 3,
					name: "121",
					descr: "1231111",
					image:
						"https://www.peoples.ru/art/cinema/actor/sasha_grey/grey_201105131531394.jpg",
					price: "10 000 руб.",
				},
				{
					id: 3,
					name: "121",
					descr: "1231111",
					image:
						"https://www.peoples.ru/art/cinema/actor/sasha_grey/grey_201105131531394.jpg",
					price: "10 000 руб.",
				},
				{
					id: 3,
					name: "121",
					descr: "1231111",
					image:
						"https://www.peoples.ru/art/cinema/actor/sasha_grey/grey_201105131531394.jpg",
					price: "10 000 руб.",
				},
				{
					id: 3,
					name: "121",
					descr: "1231111",
					image:
						"https://www.peoples.ru/art/cinema/actor/sasha_grey/grey_201105131531394.jpg",
					price: "10 000 руб.",
				},
				{
					id: 3,
					name: "121",
					descr: "1231111",
					image:
						"https://www.peoples.ru/art/cinema/actor/sasha_grey/grey_201105131531394.jpg",
					price: "10 000 руб.",
				},
				{
					id: 3,
					name: "121",
					descr: "1231111",
					image:
						"https://www.peoples.ru/art/cinema/actor/sasha_grey/grey_201105131531394.jpg",
					price: "10 000 руб.",
				},
				{
					id: 3,
					name: "121",
					descr: "1231111",
					image:
						"https://www.peoples.ru/art/cinema/actor/sasha_grey/grey_201105131531394.jpg",
					price: "10 000 руб.",
				},
				{
					id: 3,
					name: "121",
					descr: "1231111",
					image:
						"https://www.peoples.ru/art/cinema/actor/sasha_grey/grey_201105131531394.jpg",
					price: "10 000 руб.",
				},
				{
					id: 3,
					name: "121",
					descr: "1231111",
					image:
						"https://www.peoples.ru/art/cinema/actor/sasha_grey/grey_201105131531394.jpg",
					price: "10 000 руб.",
				},
				{
					id: 3,
					name: "121",
					descr: "1231111",
					image:
						"https://www.peoples.ru/art/cinema/actor/sasha_grey/grey_201105131531394.jpg",
					price: "10 000 руб.",
				},
				{
					id: 3,
					name: "121",
					descr: "1231111",
					image:
						"https://www.peoples.ru/art/cinema/actor/sasha_grey/grey_201105131531394.jpg",
					price: "10 000 руб.",
				},
				{
					id: 3,
					name: "121",
					descr: "1231111",
					image:
						"https://www.peoples.ru/art/cinema/actor/sasha_grey/grey_201105131531394.jpg",
					price: "10 000 руб.",
				},
				{
					id: 3,
					name: "121",
					descr: "1231111",
					image:
						"https://www.peoples.ru/art/cinema/actor/sasha_grey/grey_201105131531394.jpg",
					price: "10 000 руб.",
				},
				{
					id: 3,
					name: "121",
					descr: "1231111",
					image:
						"https://www.peoples.ru/art/cinema/actor/sasha_grey/grey_201105131531394.jpg",
					price: "10 000 руб.",
				},
				{
					id: 3,
					name: "121",
					descr: "1231111",
					image:
						"https://www.peoples.ru/art/cinema/actor/sasha_grey/grey_201105131531394.jpg",
					price: "10 000 руб.",
				},
				{
					id: 3,
					name: "121",
					descr: "1231111",
					image:
						"https://www.peoples.ru/art/cinema/actor/sasha_grey/grey_201105131531394.jpg",
					price: "10 000 руб.",
				},
				{
					id: 3,
					name: "121",
					descr: "1231111",
					image:
						"https://www.peoples.ru/art/cinema/actor/sasha_grey/grey_201105131531394.jpg",
					price: "10 000 руб.",
				},
				{
					id: 3,
					name: "121",
					descr: "1231111",
					image:
						"https://www.peoples.ru/art/cinema/actor/sasha_grey/grey_201105131531394.jpg",
					price: "10 000 руб.",
				},
				{
					id: 3,
					name: "121",
					descr: "1231111",
					image:
						"https://www.peoples.ru/art/cinema/actor/sasha_grey/grey_201105131531394.jpg",
					price: "10 000 руб.",
				},
				{
					id: 3,
					name: "121",
					descr: "1231111",
					image:
						"https://www.peoples.ru/art/cinema/actor/sasha_grey/grey_201105131531394.jpg",
					price: "10 000 руб.",
				},
				{
					id: 3,
					name: "121",
					descr: "1231111",
					image:
						"https://www.peoples.ru/art/cinema/actor/sasha_grey/grey_201105131531394.jpg",
					price: "10 000 руб.",
				},
				{
					id: 3,
					name: "121",
					descr: "1231111",
					image:
						"https://www.peoples.ru/art/cinema/actor/sasha_grey/grey_201105131531394.jpg",
					price: "10 000 руб.",
				},
				{
					id: 3,
					name: "121",
					descr: "1231111",
					image:
						"https://www.peoples.ru/art/cinema/actor/sasha_grey/grey_201105131531394.jpg",
					price: "10 000 руб.",
				},
				{
					id: 3,
					name: "121",
					descr: "1231111",
					image:
						"https://www.peoples.ru/art/cinema/actor/sasha_grey/grey_201105131531394.jpg",
					price: "10 000 руб.",
				},
				{
					id: 3,
					name: "121",
					descr: "1231111",
					image:
						"https://www.peoples.ru/art/cinema/actor/sasha_grey/grey_201105131531394.jpg",
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
.window {}

.main {
	display: flex;
	justify-content: flex-end;
	padding: w(32);
	background: #FFFEFB;

	&__form {
		max-width: w(332);
	}
}

.goodsList {

	width: w(1000);

	@media (max-width: 768px) {
		text-align: right;
		// width: w(800);
	}
}
</style>
