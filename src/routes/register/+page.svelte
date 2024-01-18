<script>
	let name = '';
	let email = '';
	let password = '';
	let responseMessage = '';

	async function handleSubmit() {
		try {
			const response = await fetch('http://127.0.0.1:8000/register', {
				method: 'POST',
				headers: {
					'Content-Type': 'application/json'
				},
				body: JSON.stringify({
					user_name: name,
					email,
					password
				})
			});

			const data = await response.json();

			if (data.message === 'Usuário cadastrado com sucesso!') {
				responseMessage = 'Usuário registrado com sucesso!';
			} else {
				responseMessage = 'Erro ao cadastrar. Tente novamente.';
			}
		} catch (error) {
			console.error(error);
		}
	}
</script>

<main class="w-full h-[80vh] flex justify-center items-center">
	<form
		on:submit={handleSubmit}
		class="flex flex-col items-center justify-center w-5/6 h-fit py-20  rounded-xl "
	>
		<div class="flex flex-col mb-2 w-[90%] md:w-fit">
			<label for="name" class="mr-2">Nome:</label>
			<input
				class="border-2 border-black rounded py-1 px-2 w-full md:w-[400px]"
				type="text"
				id="name"
				bind:value={name}
				required
			/>
		</div>

		<div class="flex flex-col mb-2 w-[90%] md:w-fit">
			<label for="email" class="mr-2">Email:</label>
			<input
				class="border-2 border-black rounded py-1 px-2 w-full md:w-[400px]"
				type="email"
				id="email"
				bind:value={email}
				required
			/>
		</div>

		<div class="flex flex-col mb-12 w-[90%] md:w-fit">
			<label for="password" class="mr-2">Senha:</label>
			<input
				class="border-2 border-black rounded py-1 px-2 w-full md:w-[400px]"
				type="password"
				id="password"
				bind:value={password}
				required
			/>
		</div>

		<button
			type="submit"
			class="px-12 py-4 bg-black text-white rounded-full border-2 hover:border-black hover:text-black hover:bg-white ease-out duration-300"
			>Registrar</button
		>
		{#if responseMessage}
			<p class="mt-4 text-green-500 font-bold">{responseMessage}</p>
		{/if}
	</form>
</main>
