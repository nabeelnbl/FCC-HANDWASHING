<script>
	export let name;
	let count=0;
	$: doubled = count * 2;
	function incrementCount(){
        count +=1;
		
	}
	$: console.log("the count is" + count);
	$:{
		console.log("the count is" + count);
		 //alert("the count is " + count)

	}
	$:if (count>=10){
		alert("the value is high");
		count = 9;
	}
</script>

<main>
	<h1>Hello {name}!</h1>
	<p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p>
	<button on:click={incrementCount}>click {count} {count===1?'time':"times"}</button>
	<p>the {count} double is {doubled}</p>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	button{
		color: red;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>