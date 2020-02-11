<script>
	import { Router, Route, Link } from "svelte-routing";
	
	import Home from "./Home.svelte";
	import About from "./About.svelte";
	import Blog from "./Blog.svelte";
	

	export let name;
	export let url = "";
</script>

<main>
	<h1>Hello {name}!</h1>
	<Router url="{url}">
		<nav>
			<Link to="/">Home</Link>
			<Link to="about">About</Link>
			<Link to="blog">Blog</Link>
		</nav>
		<div>
			<Route path="about" component="{About}" />
			<Route path="blog/*" component="{Blog}" />
			<Route path="/" component="{Home}" />
		</div>
	</Router>
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

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>