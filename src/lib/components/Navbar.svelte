<script lang="ts">
	import { onMount } from 'svelte';
	import { page } from '$app/state';
	import { fly } from 'svelte/transition';

	// Navigation items - use the same data structure from layout
	let navigationItems = [
		{ url: '/', text: 'Home' },
		{ url: '/about', text: 'About' },
		{ url: '/services', text: 'Services' },
		{ url: '/contact', text: 'Contact' }
	];

	let siteName = 'Brisk Solutions';
	let logoPath = '/brisklogo.jpg';

	// Mobile menu state
	let showMobileMenu = $state(false);
	let scrolled = $state(false);

	// Track scroll position to change navbar style
	function handleScroll() {
		scrolled = window.scrollY > window.innerHeight / 2;
	}

	// Toggle mobile menu
	function toggleMobileMenu() {
		showMobileMenu = !showMobileMenu;
	}

	// Close mobile menu
	function closeMobileMenu() {
		showMobileMenu = false;
	}

	// Active link class
	const activeClass = 'border-white text-white border-b-2 font-medium';

	// Inactive link class with hover effect
	const inactiveClass =
		'text-white/90 after:bg-white hover:text-white relative font-medium text-gray-700 ' +
		'after:absolute after:bottom-[-4px] after:left-0 after:h-0.5 after:w-0 ' +
		'after:transition-all after:duration-300 hover:after:w-full';

	// Update current path on mount
	onMount(() => {
		// Close mobile menu when pressing escape key
		const handleEscape = (e: KeyboardEvent) => {
			if (e.key === 'Escape' && showMobileMenu) {
				closeMobileMenu();
			}
		};

		window.addEventListener('keydown', handleEscape);

		// Add scroll event listener
		window.addEventListener('scroll', handleScroll);

		// Initial check for scroll position
		handleScroll();

		// Cleanup on component destroy
		return () => {
			window.removeEventListener('scroll', handleScroll);
			window.removeEventListener('keydown', handleEscape);
		};
	});
</script>

<header class="fixed top-0 left-0 z-50 w-full {scrolled ? 'bg-primary' : 'bg-black/20 '}">
	<div class="container mx-auto px-4 lg:px-6">
		<div class="flex h-20 items-center justify-between">
			<!-- Logo -->
			<div class="flex-shrink-0">
				<a href="/" class="flex items-center">
					<img src={logoPath} alt={siteName} class="h-14 w-auto object-contain" />
				</a>
			</div>

			<!-- Desktop Navigation -->
			<div class="hidden items-center space-x-8 font-light md:flex">
				{#each navigationItems as item}
					<a href={item.url} class={page.url.pathname === item.url ? activeClass : inactiveClass}>
						{item.text}
					</a>
				{/each}
			</div>

			<!-- Contact button (desktop) -->
			<div class="hidden items-center border border-gray-700 md:flex">
				<a href="/contact" class="bg-primary hover:bg-primary/90 rounded-md px-4 py-2 font-thin text-white transition-colors">
					Get in Touch
				</a>
			</div>

			<!-- Mobile menu button -->
			<div class="flex md:hidden">
				<button
					onclick={toggleMobileMenu}
					class="cursor-pointer rounded-md p-2 text-white/80 hover:text-white"
					aria-expanded={showMobileMenu}
					aria-label="Toggle menu"
				>
					<i class="bi bi-list text-3xl"></i>
				</button>
			</div>
		</div>
	</div>

	<!-- Mobile Menu Overlay -->
	{#if showMobileMenu}
		<div
			class="fixed inset-0 z-50 bg-black/50 md:hidden"
			onclick={closeMobileMenu}
			aria-hidden="true"
			transition:fly={{ duration: 300, opacity: 0 }}
		></div>
		<!-- Mobile Menu Panel -->
		<div class="fixed top-0 right-0 z-50 h-full w-4/5 max-w-sm bg-white shadow-xl md:hidden" transition:fly={{ duration: 300, x: 500 }}>
			<div class="flex h-full flex-col p-6">
				<div class="mb-8 flex items-center justify-between">
					<a href="/" class="flex-shrink-0">
						<img src={logoPath} alt={siteName} class="h-10 w-auto" />
					</a>
					<button onclick={closeMobileMenu} class="hover:text-primary cursor-pointer text-gray-500" aria-label="Close menu">
						<i class="bi bi-x-lg text-2xl"></i>
					</button>
				</div>

				<nav class="flex-1">
					<ul class="space-y-6">
						{#each navigationItems as item}
							<li>
								<a
									href={item.url}
									class={`block text-lg ${page.url.pathname === item.url ? 'text-primary font-medium' : 'hover:text-primary text-gray-700'}`}
									onclick={closeMobileMenu}
								>
									{item.text}
								</a>
							</li>
						{/each}
					</ul>
				</nav>

				<div class="mt-8 border-t border-gray-200 pt-6">
					<a
						href="/contact"
						class="bg-primary hover:bg-primary/90 block w-full rounded-md px-4 py-3 text-center font-medium text-white transition-colors"
						onclick={closeMobileMenu}
					>
						Get in Touch
					</a>
				</div>
			</div>
		</div>
	{/if}
</header>
