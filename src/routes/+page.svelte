<script>
	let messages = ['Bot: Hi Say anything and ill respond!'];
	let m = '';

	function addMessage() {
		if (m.trim() !== '') {
			messages.push('User: ' + m);
			messages.push('Bot: Nuh Uh');
			messages = messages;
			m = '';
		}
	}
</script>

<h1 class="text-3xl text-center font-bold pb-6 pt-2">Nuh uh bot!</h1>
<div class="flex flex-col justify-center items-center space-y-2">
	{#each messages as msg}
		<p>{msg}</p>
	{/each}
	<form on:submit|preventDefault={addMessage} class=" flex space-x-2 items-center pt-2">
		<input
			type="text"
			bind:value={m}
			class="flex-1 p-1 border rounded min-w-[400px] bg-slate-500"
		/>
		<button type="submit" class="bg-cyan-400 p-1 rounded-lg hover:bg-cyan-500"> Submit </button>
	</form>
</div>

<style lang="postcss">
	:global(body) {
		@apply bg-slate-800 text-white;
	}
</style>
