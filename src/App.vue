<template>
	<div class="header">
		<Titulo titulo="Primer pág en Vue.Js"></Titulo>
	</div>
	<div id="contenedor">
		<div id="logo">
			<img id="vue" alt="Vue logo" src="./assets/logo.png" />
			<Titulo titulo="Banco Pichincha"></Titulo>
		</div>
		<div id="cuenta">
			<Cuenta numCue="123456"></Cuenta>
		</div>
	</div>
</template>

<script>
	import Titulo from "./components/Titulo";
	import Cuenta from "./components/Cuenta";

	export default {
		name: "App",
		components: {
			Titulo,
			Cuenta,
		},
	};
</script>

<style>
	#app {
		font-family: Avenir, Helvetica, Arial, sans-serif;
		-webkit-font-smoothing: antialiased;
		-moz-osx-font-smoothing: grayscale;
		color: #2c3e50;
	}
	#contenedor {
		margin-top: 5vh;
		display: flex;
		justify-content: center;
		flex-wrap: wrap;
		width: 100%;
		height: 500px;
	}
	#logo {
		border: 8px solid;
		border-color: rgb(48, 49, 49);
		border-radius: 10%;
		display: flex;
		justify-content: center;
		flex-direction: column;
		padding: 10px;
	}
	#cuenta {
		margin-left: 10px;
	}
	#vue {
		-webkit-filter: drop-shadow(15px 15px 15px #222);
		filter: drop-shadow(15px 15px 15px #222);
	}
	.header {
		display: flex;
		justify-content: center;
	}
	@media (max-width: 411px) {
		#contenedor {
			font-size: 15px;
			margin-top: 0;
		}
	}
</style>
