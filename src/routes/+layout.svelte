<script>
	import '../app.css';
</script>

<header class="w-full h-20 flex px-8 items-center justify-between">
	<a href="/"><img src="eduq_horizontal.png" alt="" class="md:h-10 h-6" /></a>
	<nav class="hidden lg:block">
		<ul class="flex xl:space-x-40 space-x-20 font-bold xl:pl-20 justify-center">
			<li>
				<a href="." class="p-1 hover:border-b-2 hover:border-black ease-out duration-75">Conheça</a>
			</li>
			<li>
				<a href="." class="p-1 hover:border-b-2 hover:border-black ease-out duration-75">Contato</a>
			</li>
			<li>
				<a href="." class="p-1 hover:border-b-2 hover:border-black ease-out duration-75">Tutorial</a
				>
			</li>
		</ul>
	</nav>
	<div class="space-x-2 font-bold">
		<a
			href="/login"
			class="md:px-6 md:py-3 px-2 py-2 border-2 border-blue-500 rounded-full ease-out duration-300 hover:bg-blue-500 hover:text-white"
			>Login</a
		>
		<a
			href="/register"
			class="md:px-6 md:py-3 px-2 py-2 border-2 border-green-500 rounded-full ease-out duration-300 hover:bg-green-500 hover:text-white"
			>Cadastre-se</a
		>
	</div>
</header>

<slot />
