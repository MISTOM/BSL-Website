<script lang="ts">
	import '../app.css';

	let { children } = $props();
	let showMenu = $state(false);

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
		logo: '' // Add your logo URL here if you have one
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

	function toggleMenu() {
		showMenu = !showMenu;
	}
</script>

<nav>
	<div class="relative z-50 container mx-auto grid h-24 grid-cols-3 px-6">
		<div class="flex items-center">
			<!-- menu button -->
			<button onclick={() => (showMenu = true)} aria-label="Menu">
				<svg class="h-8 w-8 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
					<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"></path>
				</svg>
			</button>

			{#if showMenu}
				<div class="fixed inset-0 z-50 h-full w-full text-white">
					<div
						class="relative z-10 container mx-auto flex h-full flex-col items-center justify-center space-y-6 px-6 py-8 text-2xl font-bold tracking-widest uppercase"
					>
						<button onclick={() => (showMenu = false)} class="absolute top-0 left-0 mt-8 ml-6" aria-label="Close Menu">
							<svg class="h-8 w-8" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
								<path
									stroke-linecap="round"
									stroke-linejoin="round"
									stroke-width="2"
									d="M10 14l2-2m0 0l2-2m-2 2l-2-2m2 2l2 2m7-2a9 9 0 11-18 0 9 9 0 0118 0z"
								></path>
							</svg>
						</button>

						{#each navigationItems as item}
							<a href={item.url} class="inline-block border-b-4 border-transparent hover:border-white">
								{item.text}
							</a>
						{/each}
					</div>
					<div class="bg-opacity-20 bg-primary absolute inset-0 h-full w-full"></div>
				</div>
			{/if}
		</div>

		<div class="flex items-center justify-center">
			<a href="/" class="text-2xl font-bold tracking-widest text-white uppercase">
				<!-- logo -->
				{#if settings.logo}
					<img src={settings.logo} class="h-20 w-64 object-contain object-center" alt={settings.site_name} />
				{:else}
					{settings.site_name}
				{/if}
			</a>
		</div>

		<div class="flex items-center justify-end">
			<!-- contact button -->
			<a href="/contact" aria-label="Contact Us">
				<svg class="h-8 w-8 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
					<path
						stroke-linecap="round"
						stroke-linejoin="round"
						stroke-width="2"
						d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"
					></path>
				</svg>
			</a>
		</div>
	</div>

	<div class="bg-primary absolute top-0 left-0 h-24 w-full"></div>
</nav>

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

<style>
	/* Add any custom styles here */
	nav {
		position: relative;
	}
</style>
