<script>
	import About from "./components/About.svelte";
	import Text from "./components/Text.svelte";
	import Person from "./components/Person.svelte"
	import Skill from './components/Skill.svelte';

	export let name;
	export let lastName;
	let svelteLogo = "https://arepa.s3.amazonaws.com/svelte-logo.png";

	const data = {
		name: "Carlos",
		lastName: "Villanueva",
		age: 31,
	};
</script>

<main>
	<h1>Hello {name} {lastName}!</h1>
	<About />
	<Text anotherText="Hello Svelte Community!!!"/>
	<Person name={data.name} lastName={data.lastName} age={data.age}/>
	<Skill />
	<img src={svelteLogo} alt="Svelte logo">
</main>

<style>
	html{
		font-size: 62.5%;
	}
	:global(body){
		background-color: #f2eee2;
		color: #0084f6;
	}
	:global(root){
		--theme-color: purple;
	}

	/*estructura css global para que se active el dark-mode al documento body*/
	:global(body.dark-mode){
		background-color: #1d3040;
		color: #bfc2c7;
	}

	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	main img{
		width: 30%;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>