<svelte:head>
	<title>Cthullu Online - Comprar</title>
</svelte:head>

<script>
	import prod1 from '../../static/assets/produtos/prod3.jpg' 
	import prod2 from '../../static/assets/produtos/alone.png' 
	import prod3 from '../../static/assets/produtos/cults.png' 
	import prod4 from '../../static/assets/produtos/dark_ages.png' 
	import prod5 from '../../static/assets/produtos/dead_light.png' 
	import prod6 from '../../static/assets/produtos/harvest.png' 
	import prod7 from '../../static/assets/produtos/mansions.jpg' 
	import prod8 from '../../static/assets/produtos/nyarlathjotep.jpg' 

	let cols = 4

	let cart = [];
	let products = [
		{id: 1, name: "Trough The Ages", image: prod1, price: 10, quantity: 1},
		{id: 2, name: "Alone Against The Dark", image: prod2, price: 10, quantity: 1},
		{id: 3, name: "Cults of Cthullhu", image: prod3, price: 10, quantity: 1},
		{id: 4, name: "Dark Ages", image: prod4, price: 10, quantity: 1},
		{id: 5, name: "Dead Light", image: prod5, price: 10, quantity: 1},
		{id: 6, name: "A Time to Harvest", image: prod6, price: 10, quantity: 1},
		{id: 7, name: "Mansions of Madness", image: prod7, price: 10, quantity: 1},
		{id: 8, name: "Masks of Nyarlathotep", image: prod8, price: 10, quantity: 1},
	]
	
	const addToCart = (product) => {
		for(let item of cart) {
				if(item.id === product.id) {
					product.quantity += 1
					cart = cart;
					return;
				}
		}
		cart = [...cart, product]
	}
	
	const minusItem = (product) => {
		for(let item of cart) {
				if(item.id === product.id) {
					if(product.quantity > 1 ) {
							product.quantity -= 1
							cart = cart
					} else {
							cart = cart.filter((cartItem) => cartItem != product)
					}
					return;
				}
		}
	}
	
	const plusItem = (product) => {
		for(let item of cart) {
			if(item.id === product.id) {
				item.quantity += 1
				cart = cart;
				return;
			}
		}
	}

	$: total = cart.reduce((sum, item) => sum + item.price * item.quantity, 0)
	
</script>

<h1> Produtos </h1>
<hr>
<div class="text-center">
		{#each products as product, i}
			{#if i % 10 === 0}
<div class="container">
   
<div class="row row-cols-1 row-cols-sm-2 row-cols-md-3 row-cols-lg-4 row-cols-xl-5">
  <div class="col mb-4">
    <div class="card">
		<img src="{products[i].image}" class="card-img-top" alt="...">
      <div class="card-body">
		  <h5 class="card-title">{products[i].name}</h5>
		  <p class="card-text">${products[i].price}</p>
		  <button on:click={()=> addToCart(product)} class="btn btn-primary">Adicionar ao carrinho</button>
      </div>
    </div>
  </div>
  <div class="col mb-4">
    <div class="card">
		<img src="{products[i+1].image}" class="card-img-top" alt="...">
      <div class="card-body">
		  <h5 class="card-title">{products[i+1].name}</h5>
		  <p class="card-text">${products[i+1].price}</p>
		  <button on:click={()=> addToCart(product[i+1])} class="btn btn-primary">Adicionar ao carrinho</button>
      </div>
    </div>
  </div>
  <div class="col mb-4">
    <div class="card">
		<img src="{products[i+2].image}" class="card-img-top" alt="...">
      <div class="card-body">
		  <h5 class="card-title">{products[i+2].name}</h5>
		  <p class="card-text">${products[i+2].price}</p>
		  <button on:click={()=> addToCart(products[i+2])} class="btn btn-primary">Adicionar ao carrinho</button>
      </div>
    </div>
  </div>

<div class="col mb-4">
    <div class="card">
		<img src="{products[i+3].image}" class="card-img-top" alt="...">
      <div class="card-body">
		  <h5 class="card-title">{products[i+3].name}</h5>
		  <p class="card-text">${products[i+3].price}</p>
		  <button on:click={()=> addToCart(products[i+3])} class="btn btn-primary">Adicionar ao carrinho</button>
      </div>
    </div>
  </div>

<div class="col mb-4">
    <div class="card">
		<img src="{products[i+4].image}" class="card-img-top" alt="...">
      <div class="card-body">
		  <h5 class="card-title">{products[i+4].name}</h5>
		  <p class="card-text">${products[i+4].price}</p>
		  <button on:click={()=> addToCart(products[i+4])} class="btn btn-primary">Adicionar ao carrinho</button>
      </div>
    </div>
  </div>

<div class="col mb-4">
    <div class="card">
		<img src="{products[i+5].image}" class="card-img-top" alt="...">
      <div class="card-body">
		  <h5 class="card-title">{products[i+5].name}</h5>
		  <p class="card-text">${products[i+5].price}</p>
		  <button on:click={()=> addToCart(products[i+5])} class="btn btn-primary">Adicionar ao carrinho</button>
      </div>
    </div>
  </div>

<div class="col mb-4">
    <div class="card">
		<img src="{products[i+6].image}" class="card-img-top" alt="...">
      <div class="card-body">
		  <h5 class="card-title">{products[i+6].name}</h5>
		  <p class="card-text">${products[i+6].price}</p>
		  <button on:click={()=> addToCart(products[i+6])} class="btn btn-primary">Adicionar ao carrinho</button>
      </div>
    </div>
  </div>



</div>
</div>
			{/if}

	{/each}

<div class="cart-list">
	{#each cart as item }
		{#if item.quantity > 0}
		<div class="card">
			<img width="50" src={item.image} alt={item.name}/>
			<div>{item.quantity}
				<button on:click={() => plusItem(item)}>+</button>
				<button on:click={() => minusItem(item)}>-</button>
			</div>
			<p>${item.price * item.quantity}</p>
		</div>
		{/if}
	{/each}
	<div class="total">
		<h4>Total: ${total}</h4>
	</div>
</div>
</div>

<style>
@media (max-width: 576px) {  
  .xs {color:red;font-weight:bold;}
}

/* Small devices (landscape phones, 576px and up) */
@media (min-width: 576px) and (max-width:768px) {  
  .sm {color:red;font-weight:bold;}
}
 
/* Medium devices (tablets, 768px and up) The navbar toggle appears at this breakpoint */
@media (min-width: 768px) and (max-width:992px) {  
 .md {color:red;font-weight:bold;}
}
 
/* Large devices (desktops, 992px and up) */
@media (min-width: 992px) and (max-width:1200px) { 
 .lg {color:red;font-weight:bold;}
}
 
/* Extra large devices (large desktops, 1200px and up) */
@media (min-width: 1200px) {  
    .xl {color:red;font-weight:bold;}
}
 </style>
