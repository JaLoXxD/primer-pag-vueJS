<template>
	<h2>N° Cuenta: {{ numCue }}</h2>
	<h2>Tipo de cuenta: {{ cuenta }}</h2>
	<h2>Propietario: {{ propietario }}</h2>
	<h2 :class = "[myClass]">Saldo: {{ saldo }}</h2>
	<h2 v-if="saldo === 0" class = "noMoney">Ya no tienes dinero</h2>
	<h2>Estado: {{ estado ? "Activa" : "Inactiva" }}</h2>
	<h2>Servicios disponibles:</h2>
	<h2 v-for="(servicio, index) in servicios" :key="index">{{ index + 1 }}) {{ servicio }}</h2>
	<div class="buttons">
		<AccionSaldo text="Aumentar" @accion="aumentarSaldo" id="button1"></AccionSaldo>
		<AccionSaldo text="Disminuir" :disable="disable" @accion="disminuirSaldo" id="button2"></AccionSaldo>
	</div>
</template>

<script>
	import AccionSaldo from "./AccionSaldo";

	export default {
		name: "Cuenta",
		props: {
			numCue: String,
		},
		data() {
			return {
				propietario: "Jorge Hidalgo",
				saldo: 1000,
				cuenta: "Corriente",
				estado: true,
				servicios: ["giro", "abono", "transferencia"],
				disable: false,
			};
		},
		components: {
			AccionSaldo,
		},
		methods: {
			aumentarSaldo() {
				this.saldo = this.saldo + 100;
				if(this.saldo > 0) this.disable = false;
			},
			disminuirSaldo() {
				this.saldo = this.saldo - 100;
				if(this.saldo === 0){
					this.disable = true;
					return;
				}
			},
		},
		computed: {
			myClass(){
				if(this.saldo === 0) return 'noMoney';
				if(this.saldo > 0 && this.saldo < 500) return 'warn'
				if(this.saldo >= 500) return 'yesMoney'
			}
		}
	};
</script>

<style>
	#button2 {
		margin-left: 10px;
	}
	.noMoney {
		color: rgb(255, 0, 0);
	}
	.yesMoney {
		color: #40b883;
	}
	.warn {
		color: rgb(236, 164, 9)
	}
</style>
