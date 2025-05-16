<script lang="ts">
	import '../app.css';
	import Navbar from '$lib/components/Navbar.svelte';

	let { children } = $props();

	// Example navigation items - replace with your actual data
	const navigationItems = [
		{ url: '/', text: 'Home' },
		{ url: '/about', text: 'About' },
		{ url: '/services', text: 'Services' },
		{ url: '/contact', text: 'Contact' }
	];

	// Site settings - customize as needed
	const settings = {
		site_name: 'Brisk Solutions',
		logo: '/brisklogo.jpg' // Updated with the logo path
	};

	// Footer settings - customize as needed
	const footer = {
		copyright: '© 2025 Brisk Solutions. All rights reserved.',
		section_one_title: 'Company',
		section_one_links: [
			{ url: '/about', text: 'About Us' },
			{ url: '/team', text: 'Our Team' },
			{ url: '/careers', text: 'Careers' }
		],
		section_two_title: 'Services',
		section_two_links: [
			{ url: '/services/web-development', text: 'Web Development' },
			{ url: '/services/mobile-apps', text: 'Mobile Apps' },
			{ url: '/services/cloud-solutions', text: 'Cloud Solutions' }
		],
		section_three_title: 'Resources',
		section_three_links: [
			{ url: '/blog', text: 'Blog' },
			{ url: '/case-studies', text: 'Case Studies' },
			{ url: '/faq', text: 'FAQ' }
		]
	};
</script>

<Navbar />

{@render children()}

<footer class="text-opacity-40 bg-opacity-80 bg-gray-900 px-12 text-xs font-semibold tracking-widest text-white uppercase">
	<div class="container mx-auto grid grid-cols-1 gap-12 py-24 text-center lg:grid-cols-4 lg:text-left">
		<div>
			<div class="font-display text-4xl text-white opacity-50">{settings.site_name}</div>
		</div>
		<div>
			<div class="font-display mb-6 text-sm tracking-widest text-white uppercase">
				{footer.section_one_title}
			</div>
			{#each footer.section_one_links as item}
				<a href={item.url} class="mb-4 block">{item.text}</a>
			{/each}
		</div>
		<div>
			<div class="font-display mb-6 text-sm tracking-widest text-white uppercase">
				{footer.section_two_title}
			</div>
			{#each footer.section_two_links as item}
				<a href={item.url} class="mb-4 block">{item.text}</a>
			{/each}
		</div>
		<div>
			<div class="font-display mb-6 text-sm tracking-widest text-white uppercase">
				{footer.section_three_title}
			</div>
			{#each footer.section_three_links as item}
				<a href={item.url} class="mb-4 block">{item.text}</a>
			{/each}
		</div>
	</div>
	<div class="font-heading pb-24 text-center text-sm font-light tracking-widest text-white uppercase opacity-75 lg:text-base">
		{footer.copyright}
	</div>
</footer>
