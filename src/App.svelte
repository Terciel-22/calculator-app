<script>
	export let result;

	const handleClick = (event) => {
		result += event.target.value;
	}
	const clearResult = () => {
		result = '';
	}
	const calculateResult = () => {
		if(result != '')
		{
			result = eval(result);
		}
	}
</script>

<main>
	<div class="calculator">
		<input type="text" bind:value={result} readonly>
		<div class="buttons">
			<button on:click={handleClick} value="1">1</button>
			<button on:click={handleClick} value="2">2</button>
			<button on:click={handleClick} value="3">3</button>
			<button class="operation" on:click={handleClick} value="+">+</button>
			<button class="operation" on:click={handleClick} value="-">-</button>
			<button on:click={handleClick} value="4">4</button>
			<button on:click={handleClick} value="5">5</button>
			<button on:click={handleClick} value="6">6</button>
			<button class="operation" on:click={handleClick} value="*">*</button>
			<button class="operation" on:click={handleClick} value="/">/</button>
			<button on:click={handleClick} value="7">7</button>
			<button on:click={handleClick} value="8">8</button>
			<button on:click={handleClick} value="9">9</button>
			<button class="operation" on:click={handleClick} value="**">X<sup>n</sup></button>
			<button class="operation" on:click={handleClick} value=".">.</button>
			<button on:click={handleClick} value="(">(</button>
			<button on:click={handleClick} value="0">0</button>
			<button on:click={handleClick} value=")">)</button>
			<button class="operation" on:click={calculateResult}>=</button>
			<button class="operation" on:click={clearResult}>C</button>
		</div>
	</div>
</main>

<style>
	main {
		min-height: 100vh;
		display: flex;
		justify-content: center;
		align-items: center;
	}
	.calculator {
		max-width: 300px;
		margin: 0 auto;
		padding: 1rem;
		background-color: #f4f4f4;
		border: 1px solid #ccc;
		box-shadow: 3px 3px 3px rgba(0, 0, 0, 0.1);
		display: flex;
		flex-direction: column;
		align-items: center;
		gap: 0.5rem;
	}
	input[type="text"] {
		width: 90%;
		margin-bottom: 10px;
		font-size: 24px;
		padding: 10px;
		text-align: end;
		outline: none;
	}
	.buttons {
		display: grid;
		grid-template: 1fr 1fr 1fr 1fr / 1fr 1fr 1fr 1fr 1fr;
		gap: 0.2rem;
	}
	button {
		width: 50px;
		height: 50px;
		font-size: 1rem;
		border: none;
		background-color: rgb(27,30,38);
		color: white;
		border-radius: 5px;
		cursor: pointer;
		opacity: 0.9;
	}
	button.operation {
		background-color: rgba(39,43,46,0.7);
	}
	button:hover {
		opacity: 1;
	}
	
	@media screen and (max-width:756px)
	{

	}
</style>