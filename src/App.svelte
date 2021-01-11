<script lang="ts">
	import Header from './Header.svelte';
	import Summary from './Summary.svelte';
	import Projects from './Projects.svelte';
	import Writing from './Writing.svelte';
	import Contact from './Contact.svelte';
	
	const data = {
		summary: {
			header: "Hey! I'm Alec.",
			points: [
				"I'm a software developer, writer, and freshman majoring in CS\
				and Stats at University of Illinois at Urbana-Champaign.",
				"I'm an incoming computer graphics software engineering intern\
				at Brunswick. I've also worked on a plethora of personal and\
				group projects that you can check out in the ~projects section~\
				of this website.",
				"When I'm not working, I like to write, cook, and watch movies.",
				"",
			],
		},
		projects: [
			{
				image: "RunnerGame3.gif",
				title: "Platform Runner Game",
				stack: [
					"Rust",
					"WebAssembly",
					"Javascript",
					"WebGL",
				],
				description: "Bla bla bla"
			},
		],
		writing: [
			{
				title: "Weekly 5: How I Approach Shifting My Mindset",
				link: "https://alecchendev.medium.com/weekly-5-how-i-approach-shifting-my-mindset-38ce6525ef44?sk=7807755664969fc209f138a113058c8c",
				category: "tech"
			},
			{
				title: "Weekly 5: How I Approach Shifting My Mindset",
				link: "https://alecchendev.medium.com/weekly-5-how-i-approach-shifting-my-mindset-38ce6525ef44?sk=7807755664969fc209f138a113058c8c",
				category: "tech"
			},
			{
				title: "Weekly 5: How I Approach Shifting My Mindset",
				link: "https://alecchendev.medium.com/weekly-5-how-i-approach-shifting-my-mindset-38ce6525ef44?sk=7807755664969fc209f138a113058c8c",
				category: "tech"
			},
			{
				title: "Weekly 5: How I Approach Shifting My Mindset",
				link: "https://alecchendev.medium.com/weekly-5-how-i-approach-shifting-my-mindset-38ce6525ef44?sk=7807755664969fc209f138a113058c8c",
				category: "other"
			},
			{
				title: "Weekly 5: How I Approach Shifting My Mindset",
				link: "https://alecchendev.medium.com/weekly-5-how-i-approach-shifting-my-mindset-38ce6525ef44?sk=7807755664969fc209f138a113058c8c",
				category: "other"
			},
		],
		contact: {
			email: "mailto:alecchendev@gmail.com",
			github: "https://github.com/alecchendev",
			medium: "https://alecchendev.medium.com/",
			linkedin: "https://linkedin.com/in/alec-chen-450273182/",
		}
	};
	let menu = 0;
	const sectionKey = {
		"summary": 0,
		"projects": 1,
		"writing": 2, 
	};
	const navigate = (section) => menu = sectionKey[section];
	
</script>

<style>
	.wrapper {
		width: 50%;

		margin: auto;
		padding-top: 50px;
	}
	.contentWrapper {
		margin-top: 100px;
	}
</style>

<div class="wrapper">
	<Header navigate={(section) => navigate(section)} />
	<div class="contentWrapper">
		{#if menu === 0}
			<Summary data={data.summary} />
		{:else if menu === 1}
			<Projects projects={data.projects} />
		{:else if menu === 2}
			<Writing data={data.writing} />
		{/if}
	</div>
	<Contact data={data.contact} />
</div>
