<template>
	<button @click="accion" :disabled="disable" class="buttons"
		><span>{{ text }} Saldo </span></button
	>
</template>

<script>
	export default {
		name: "AccionSaldo",
		props: {
			text: String,
			disable: {
				type: Boolean,
				default: false,
			},
		},
		data() {
			return {};
		},
		methods: {
			accion() {
				this.$emit("accion");
			},
		},
	};
</script>

<style scoped>
	@import url("https://fonts.googleapis.com/css2?family=Ubuntu+Mono:wght@700&display=swap");
	.buttons {
		border-radius: 4px;
		background-color: #40b883;
		border: none;
		color: #ffffff;
		text-align: center;
		font-size: 18px;
		padding: 10px;
		width: 200px;
		transition: all 0.5s;
		cursor: pointer;
		margin: 5px;
		font-family: "Ubuntu Mono", monospace;
	}

	.buttons span {
		cursor: pointer;
		display: inline-block;
		position: relative;
		transition: 0.5s;
	}

	.buttons span:after {
		content: "\00bb";
		position: absolute;
		opacity: 0;
		top: 0;
		right: -20px;
		transition: 0.5s;
	}

	.buttons:hover span {
		padding-right: 25px;
	}

	.buttons:hover span:after {
		opacity: 1;
		right: 0;
	}

	@media (max-width: 411px) {
		.buttons{
			width: 100px;
			font-size: 12px;
		}
	}
</style>
