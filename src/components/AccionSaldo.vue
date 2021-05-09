<template>
	<button @click = "accion" :disabled = "disable" class="buttons">{{ text }} Saldo</button>
</template>

<script>
	export default {
		name: "AccionSaldo",
		props: {
			text: String,
			disable: {
				type: Boolean,
				default: false
			},
		},
		data() {
			return {};
		},
		methods: {
			accion() {
				this.$emit('accion');
			},
		},
	};
</script>

<style>
	@import url('https://fonts.googleapis.com/css2?family=Ubuntu+Mono:wght@700&display=swap');
	.buttons{
		padding: 8px;
		font-family: 'Ubuntu Mono', monospace;;
		font-size: 15px;
	}
</style>
