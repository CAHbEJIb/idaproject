<template>
	<header class="header">
		<h2 class="header__title">Добавление товара</h2>
		<div class="header__select header-select">По умолчанию
			<div class="header-select__arrow"></div>
		</div>
	</header>
</template>
<script>export default { data() { return {} } }
</script>
<style scoped lang="scss">
.header {
	display: flex;
	justify-content: space-between;
	margin-bottom: w(16);

	&__title {
		font-size: w(28);
		line-height: w(35);
		font-weight: 600;
		letter-spacing: 0em;
		text-align: left;
		color: $titleColor;
	}

	&__select {
		font-size: w(12);
		padding: w(10) w(12);
		background: $backFormBlock;
		box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.1);
		border-radius: 4px;
		color: $placeholderColor;
		display: flex;
		align-items: center;
		gap: w(5);
	}
}

.header-select {
	pointer-events: none;
	max-height: w(36);

	&__arrow {
		transform: rotate(45deg);
		border-bottom: 1px solid $placeholderColor;
		border-right: 1px solid $placeholderColor;
		width: w(4);
		height: w(4);
	}
}
</style>