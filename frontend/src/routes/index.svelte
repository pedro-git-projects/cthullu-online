<svelte:head>
	<title>Cthullu Online - Home</title>
</svelte:head>
<script>
	import cultist from '../../static/assets/home_image_3.png';
	import { goto } from '@sapper/app'
</script>

<main>

	<div class="container">
		<div class="row">
			<div class="col text-center mb-3">
				<h1> Cthullu Online</h1>
			</div>
		</div>
	</div>

	<div class="container">
		<div class="row">
			<div class="col text-center mb-3">
				Bem vindo ao <b>Cthullu Online</b>, um site onde você
				pode gerar investigadores para a sétima edição do jogo 
				<i>Call of Cthullu</i> da Chaosium.			
			</div>
		</div>
	</div>

	<div class="container">
		<div class="row">
			<div class="col text-center">
				<button on:click={() => goto('/criar')} class="btn btn-primary">Criar</button>
			</div>
		</div>
	</div>

	<div class="container mt-0">
		<div class="row text-center">
			<figure>
				<img alt="Cultist" class="img-fluid" src="{cultist}">
			</figure>
		</div>
	</div>



</main>

<style>
	h1 {
		font-family: 'Macondo', cursive;
	}
</style>
