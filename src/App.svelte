<script>
	let usernameInputField = '';
</script>

<main>
	<form>
		<label for="usernam">Enter a Github username:</label>
		<input type="text" name="username" placeholder="Enter Username" bind:value={usernameInputField} />
		<button type="submit">Load repositories</button>
	</form>
</main>

<style>
	main {
		width:80%;
		max-width: 800px;
		margin: 20px auto;
		padding: 20px;
	}

	label {
		font-weight: bold;
	}

	input {
		widows: 80%;
	}

</style>