<script lang="ts">
	import Header from './Header.svelte';
	import Summary from './Summary.svelte';
	import Projects from './Projects.svelte';
	import Writing from './Writing.svelte';
	import Contact from './Contact.svelte';
	
	const data = {
		summary: {
			image: "MyPhoto.jpg",
			header: "Hey! I'm Alec.",
			points: [
				"I'm a software developer, writer, and freshman majoring in CS\
				and Stats at University of Illinois at Urbana-Champaign.",
				"I'm an incoming computer graphics software engineering intern\
				at Brunswick. I've also worked on a plethora of personal and\
				group projects that you can check out in the ~projects section~\
				of this website.",
				"When I'm not working, I like to write, cook, and watch movies.",
			],
		},
		projects: [
			{
				image: "RunnerGame.gif",
				title: "Platform Runner Game",
				stack: [
					"Rust",
					"WebAssembly",
					"Javascript",
					"WebGL",
				],
				description: "A simple 3D platformer game where you traverse levels as fast as you can using a spiderman-esque grappling hook ability. I didn't use a game engine, so I had to work with the graphics directly, and craft my own physics/collision system. It was difficult, but I learned a lot, and I think it turned out pretty well.",
			},
			{
				image: "3DEngine.gif",
				title: "3D Graphics Engine From Scratch",
				stack: [
					"C++",
					"Cinder",
				],
				description: "Given 3-4 weeks to make something using C++ and the graphics API Cinder, I set out to build the systems behind transforming 3D perspective to a 2D screen. After a lot of pacing around my dorm room, I developed a system with simple lighting that could render a first person perspective moving around inside of a room.",
			},
			{
				image: "Nutribuddy.gif",
				title: "Nutribuddy",
				stack: [
					"Javascript",
					"React",
					"Python",
					"Flask",
				],
				description: "Here I served as the frontend developer on a nutrition recommendation web app my team called Nutribuddy. Working together we cranked out a pretty sleek MVP that takes in a user's dietary preferences and restrictions, and outputs a week's worth of curated meals.",
			},
			{
				image: "SocialNetwork.png",
				title: "Social Network Analysis",
				stack: [
					"Python",
					"Matplotlib",
					"Networkx",
				],
				description: "Getting into network analysis through research during high school, I collected friendship data through survey responses and wrote an article with my analysis and visualization of the social network of those around me. I tried really hard to break down the raw statistics into more digestible insights, and it was really cool to get responses from classmates that'd read my piece.",
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
	const navigate = (section) => {
		menu = sectionKey[section];
	};
	
</script>

<style>
	.wrapper {
		width: 950px;

		margin: auto;
		padding-top: 100px;
		padding-bottom: 100px;
	}
	.contentWrapper {
		margin-top: 100px;
	}

	@media screen and (max-width: 1080px) {
        .wrapper {
			width: 90%;
		}
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
