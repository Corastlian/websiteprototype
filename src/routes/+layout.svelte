<script lang="ts">
	import './layout.css';
	import favicon from '$lib/assets/favicon.svg';
	import { Navbar, NavBrand, NavLi, NavUl, NavHamburger } from 'flowbite-svelte';
	import { fly } from 'svelte/transition';

	let { children } = $props();
</script>

<svelte:head><link rel="icon" href={favicon} /></svelte:head>
{@render children()}

<Navbar>
	<NavBrand href="/">
		<span class="self-center text-xl font-semibold whitespace-nowrap dark:text-white">
			Andy Then
		</span>
	</NavBrand>

	<NavHamburger />

	<NavUl transition={fly} transitionParams={{ y: -20, duration: 250 }}>
		<NavLi href="/experience">Experience</NavLi>
		<NavLi href="/projects">Projects</NavLi>
		<NavLi href="/posts">Posts</NavLi>
		<NavLi href="/research">Research</NavLi>
	</NavUl>
</Navbar>
