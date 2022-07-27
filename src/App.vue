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
						"https://downloader.disk.yandex.ru/preview/cffbb5dc9f3c267bf1958b01f1a5e9c014e3b5c9ad12d8fc8eb6ec552d6d811e/62e16985/DSsmqgwZhrzAlQ63iTZxxsnVUk-KV1oSotfYKTruEiWWjbs_C8wNjqClXUPV7JVt-_ozHhJgah7IUoKKcgp_iA%3D%3D?uid=0&filename=camera.jpg&disposition=inline&hash=&limit=0&content_type=image%2Fjpeg&owner_uid=0&tknv=v2&size=2048x2048",
					price: "10 000 руб.",
				},
				{
					id: 2,
					name: "Наименование товара",
					descr: "Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк",
					image:
						"https://downloader.disk.yandex.ru/preview/cffbb5dc9f3c267bf1958b01f1a5e9c014e3b5c9ad12d8fc8eb6ec552d6d811e/62e16985/DSsmqgwZhrzAlQ63iTZxxsnVUk-KV1oSotfYKTruEiWWjbs_C8wNjqClXUPV7JVt-_ozHhJgah7IUoKKcgp_iA%3D%3D?uid=0&filename=camera.jpg&disposition=inline&hash=&limit=0&content_type=image%2Fjpeg&owner_uid=0&tknv=v2&size=2048x2048",
					price: "10 000 руб.",
				},
				{
					id: 3,
					name: "Наименование товара",
					descr: "Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк",
					image:
						"https://downloader.disk.yandex.ru/preview/cffbb5dc9f3c267bf1958b01f1a5e9c014e3b5c9ad12d8fc8eb6ec552d6d811e/62e16985/DSsmqgwZhrzAlQ63iTZxxsnVUk-KV1oSotfYKTruEiWWjbs_C8wNjqClXUPV7JVt-_ozHhJgah7IUoKKcgp_iA%3D%3D?uid=0&filename=camera.jpg&disposition=inline&hash=&limit=0&content_type=image%2Fjpeg&owner_uid=0&tknv=v2&size=2048x2048",
					price: "10 000 руб.",
				},
				{
					id: 4,
					name: "Наименование товара",
					descr: "Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк",
					image:
						"https://downloader.disk.yandex.ru/preview/cffbb5dc9f3c267bf1958b01f1a5e9c014e3b5c9ad12d8fc8eb6ec552d6d811e/62e16985/DSsmqgwZhrzAlQ63iTZxxsnVUk-KV1oSotfYKTruEiWWjbs_C8wNjqClXUPV7JVt-_ozHhJgah7IUoKKcgp_iA%3D%3D?uid=0&filename=camera.jpg&disposition=inline&hash=&limit=0&content_type=image%2Fjpeg&owner_uid=0&tknv=v2&size=2048x2048",
					price: "10 000 руб.",
				},
				{
					id: 5,
					name: "Наименование товара",
					descr: "Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк",
					image:
						"https://downloader.disk.yandex.ru/preview/cffbb5dc9f3c267bf1958b01f1a5e9c014e3b5c9ad12d8fc8eb6ec552d6d811e/62e16985/DSsmqgwZhrzAlQ63iTZxxsnVUk-KV1oSotfYKTruEiWWjbs_C8wNjqClXUPV7JVt-_ozHhJgah7IUoKKcgp_iA%3D%3D?uid=0&filename=camera.jpg&disposition=inline&hash=&limit=0&content_type=image%2Fjpeg&owner_uid=0&tknv=v2&size=2048x2048",
					price: "10 000 руб.",
				},
				{
					id: 6,
					name: "Наименование товара",
					descr: "Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк",
					image:
						"https://downloader.disk.yandex.ru/preview/cffbb5dc9f3c267bf1958b01f1a5e9c014e3b5c9ad12d8fc8eb6ec552d6d811e/62e16985/DSsmqgwZhrzAlQ63iTZxxsnVUk-KV1oSotfYKTruEiWWjbs_C8wNjqClXUPV7JVt-_ozHhJgah7IUoKKcgp_iA%3D%3D?uid=0&filename=camera.jpg&disposition=inline&hash=&limit=0&content_type=image%2Fjpeg&owner_uid=0&tknv=v2&size=2048x2048",
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
	padding: w(30);
	height: 100vh;
	display: flex;
}

.goodsList {
	// position: absolute;
	// top: 0;
	// left: w(380);
	// margin-top: w(83);
	max-width: w(1028);
	display: inline-flex;
	flex-wrap: wrap;
	justify-content: flex-start;
	gap: w(16);

	@media (max-width: 768px) {
		text-align: right;
		// width: w(800);
	}
}
</style>
