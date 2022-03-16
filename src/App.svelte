<script>
	let limit = 10;
	let random;

	function guess() {
		random = Math.floor(Math.random() * limit) + 1;
	}

	$: result = typeof random !== "undefined" ? random % 2 ? "Winner 🏆" : "Looser 🤪" : "";

</script>

<main>
	<p class="result">Welcome 🤓!</p>
	<h1>Guess the <span>Odd Number</span> to win!</h1>

	<p>Guess a number between 1 to &nbsp; <input type="number" bind:value={limit} /></p>

	<button on:click={guess}>Click to guess!</button>

	<h2>You guessed <span>{random || "nothing"}!</span></h2>
	<p class="result">{result}</p>

</main>

<style>
	
	main {
		text-align: center;
		margin-top: 10vh
	}

	span {
		color: #0191ff;
		font-weight: inherit;
		margin: 0 5px;
	}
	
	input {
		padding: 0.5rem;
		outline: none;
		border: 1px solid #f3f3f3;
		box-shadow: 0px 5px 5px #b8b8b8;
		border-radius: 5px;
	}

	input:hover, input:focus {
		outline: none;
		border: 1px solid lightgray;
		box-shadow: 0px 0px 3px #daf6ff;

	}

	button {
		border: none;
		background-color: #0191ff;
		color: white;
		padding: 0.5rem 1rem;
		outline: none;
		border-radius: 5px;
		box-shadow: 0px 5px 10px #c4effd;

	}
	button:active{
		background-color: #0060ba;
		outline: none;
	}

	.result {
		font-size: 5rem;
		animation: ease-in 0.5s;
	}
</style>