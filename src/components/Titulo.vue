<template>
	<h1 class="tit1">{{ titulo }}</h1>
</template>

<script>
    

	export default {
	    name: 'Titulo',
	    props: {
	        titulo: String,
	    },
        data() {
            return {

            }
        },
        components: {
        }
	}
</script>

//SCOPED SIGNIFICA QUE LOS ESTILOS FUNCIONAN SOLO PARA ESTE COMPONENTE
<style>
    .tit1{
        color: #40B883;
    }
</style>
