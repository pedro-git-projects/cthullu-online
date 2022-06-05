<script>
	export let segment;
	import Toggle from './Toggle.svelte'
</script>

<main>
	<nav id="nav" class="navbar navbar-expand-lg navbar-dark bg-dark">
		<div class="container-fluid">
			<div class="navbar-brand" to="/"><a aria-current="{segment === undefined ? 'page' : undefined}" href=".">Cthullu Online</a></div>

			<button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
				<span class="navbar-toggler-icon"></span>
			</button>

			<div class="collapse navbar-collapse" id="navbarNav">
				<ul class="navbar-nav">

					<li class="nav-item">
						<div class="nav-link" to="/instrucoes"><a aria-current="{segment === 'instrucoes' ? 'page' : undefined}" href="instrucoes">Instruções</a></div>
					</li>

					<li class="nav-item">
						<div class="nav-link" to="/lovecraft"><a aria-current="{segment === 'lovecraft' ? 'page' : undefined}" href="lovecraft">Lovecraft</a></div>
					</li>
					<li class="nav-item">
						<div class="nav-link" to="/criar"><a aria-current="{segment === 'criar' ? 'page' : undefined}" href="criar">Criar</a></div>
					</li>	 
					<li class="nav-item">
						<div class="nav-link" to="/comprar"><a aria-current="{segment === 'comprar' ? 'page' : undefined}" href="comprar">Comprar</a></div>
					</li>
					<li class="nav-item">
						<div class="nav-link" to="/fanart"><a aria-current="{segment === 'fanart' ? 'page' : undefined}" href="fanart">Galeria</a></div>
					</li>
					<li class="nav-item">
						<div class="nav-link" to="/fonte"><a aria-current="{segment === 'fonte' ? 'page' : undefined}" href="fonte">Código Fonte</a></div>
					</li>
					<Toggle/>
				</ul>
			</div>
		</div>
	</nav>
</main>

<style>
	.navbar-brand {
		font-family: 'Macondo', cursive;
	}

	:root{
		--bg-color: #FFFFFF;
		--text-color: #000000;
		--link-color: #FFFFFF;
		--bootstrap-nav: #212529;
	}

	:global(body) {
		background: var(--bg-color);
		color: var(--text-color);
		transition: background-color 0.3s
	}

	:global(body.dark) {
		--bg-color: #000000;
		--text-color: #FFFFFF;
	}

	:global(a) {
		color: var(--link-color);
		text-decoration: none;
	}

	:global(a.dark) {
		color: #000000;
		text-decoration: none;
	}
</style>
