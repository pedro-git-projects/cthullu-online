<svelte:head>
	<title>Cthullu Online - Criar</title>
</svelte:head>

<script>
let disabled = false
let promise = Promise.resolve([])

let nome = ''
let idade = '' 
let residencia = '' 
let nascimento = '' 
let ocupacao = ''  

let caracteristicas = []

function submitForm() {
	promise = fetchInvestigador()
}

async function fetchInvestigador() {
	const response = await self.fetch('http://localhost:4000/v1/criar', {
		method: "POST",
		body: JSON.stringify({
			  nome,	
			  idade,
			  residencia,
			  nascimento,
			  ocupacao,
		  })
	});

		if (response.ok) {
  		return response.json();
			
		} else {
			throw new Error();
		}
	}
</script>

<main>
 <h1>Criar Personagens </h1>
 <form on:submit|preventDefault={submitForm}>
        <label for="nome"> <strong> Nome </strong> </label>
		<input bind:value="{nome}" id="nome" name="nome" type="text" />

        <label for="idade"> <strong> Idade </strong> </label>
		<input bind:value="{idade}" id="idade" name="idade" type="number" />

	<label for="residencia"> <strong> Residencia </strong> </label>
	<input bind:value="{residencia}" id="residencia" name="residencia" type="text" />

	<label for="nascimento"> <strong> Nascimento </strong> </label>
	<input bind:value="{nascimento}" id="nascimento" name="nascimento" type="text" />

	<label for="ocupacao"> <strong> Ocupacao </strong> </label>
	<input bind:value="{ocupacao}" id="ocupacao" name="ocupacao" type="text" />
        <br />
        <button type="submit">Save</button>
		</form>


{#await promise}
	<div></div>
{:then caracteristicas}
    <h3>{caracteristicas.investigator.name}</h3>
    <h3>{caracteristicas.investigator.age}</h3>
    <h3>{caracteristicas.investigator.residence}</h3>
    <h3>{caracteristicas.investigator.birthplace}</h3>
    <h3>{caracteristicas.investigator.occupation}</h3>
    <h3>{caracteristicas.investigator.str}</h3>
    <h3>{caracteristicas.investigator.con}</h3>
    <h3>POW: {caracteristicas.investigator.pow}</h3>
{:catch error}
	<p style="color: red">{error.message}</p>
{/await}
	
</main>

<style>
</style>
