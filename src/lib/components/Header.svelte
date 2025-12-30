<script lang="ts">
	import { page } from '$app/stores';

	let scrolled = false;
	let mobileMenuOpen = false;

	if (typeof window !== 'undefined') {
		window.addEventListener('scroll', () => {
			scrolled = window.scrollY > 20;
		});
	}

	const navItems = [
		{ label: 'Home', href: '/' },
		{ label: 'About', href: '/about' },
		{ label: 'Facilities', href: '/facilities' },
		{ label: 'Events', href: '/events' },
		{ label: 'Guest Rooms', href: '/rooms' },
		{ label: 'Gallery', href: '/gallery' },
		{ label: 'Contact', href: '/contact' }
	];
</script>

<header
	class="fixed top-0 left-0 right-0 z-50 transition-all duration-500"
	class:scrolled
>
	<div class="absolute inset-0 bg-white/95 backdrop-blur-md border-b transition-all duration-500 {scrolled ? 'border-amber-900/10 shadow-lg' : 'border-transparent'}"></div>

	<nav class="relative container mx-auto px-4 sm:px-6 lg:px-8">
		<div class="flex items-center justify-between h-20 lg:h-24 transition-all duration-500"
			class:lg:h-20={scrolled}
		>
			<!-- Logo -->
			<a href="/" class="flex flex-col group">
				<span class="text-2xl lg:text-3xl font-bold text-primary tracking-tight font-serif transition-all duration-500"
					class:lg:text-2xl={scrolled}
				>
					Union Club
				</span>
				<span class="text-xs tracking-[0.2em] text-gold uppercase mt-0.5 opacity-75 group-hover:opacity-100 transition-opacity">
					Est. 1856
				</span>
			</a>

			<!-- Desktop Navigation -->
			<ul class="hidden lg:flex items-center space-x-1 xl:space-x-2">
				{#each navItems as item}
					<li>
						<a
							href={item.href}
							class="px-3 xl:px-4 py-2 text-sm font-medium tracking-wide transition-all duration-300 relative group"
							class:text-gold={$page.url.pathname === item.href}
							class:text-primary={$page.url.pathname !== item.href}
						>
							<span class="relative z-10">{item.label}</span>
							<span class="absolute inset-0 bg-gold/5 scale-0 group-hover:scale-100 transition-transform duration-300 rounded"></span>
							{#if $page.url.pathname === item.href}
								<span class="absolute bottom-0 left-1/2 -translate-x-1/2 w-1 h-1 bg-gold rotate-45"></span>
							{/if}
						</a>
					</li>
				{/each}
			</ul>

			<!-- Mobile Menu Button -->
			<button
				class="lg:hidden p-2 text-primary hover:text-gold transition-colors"
				on:click={() => mobileMenuOpen = !mobileMenuOpen}
				aria-label="Toggle menu"
			>
				<svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
					{#if mobileMenuOpen}
						<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
					{:else}
						<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
					{/if}
				</svg>
			</button>
		</div>

		<!-- Mobile Menu -->
		{#if mobileMenuOpen}
			<div class="lg:hidden pb-6 animate-in slide-in-from-top duration-300">
				<ul class="space-y-1">
					{#each navItems as item}
						<li>
							<a
								href={item.href}
								class="block px-4 py-3 text-base font-medium transition-all duration-300 border-l-2 {$page.url.pathname === item.href ? 'border-gold bg-gold/5 text-gold' : 'border-transparent text-primary'}"
								on:click={() => mobileMenuOpen = false}
							>
								{item.label}
							</a>
						</li>
					{/each}
				</ul>
			</div>
		{/if}
	</nav>

	<!-- Decorative bottom border -->
	<div class="absolute bottom-0 left-0 right-0 h-px bg-gradient-to-r from-transparent via-gold/30 to-transparent"></div>
</header>

<style>
	header {
		font-family: 'Crimson Text', serif;
	}

	.font-serif {
		font-family: 'Cormorant Garamond', serif;
	}

	@keyframes slide-in-from-top {
		from {
			opacity: 0;
			transform: translateY(-10px);
		}
		to {
			opacity: 1;
			transform: translateY(0);
		}
	}

	.animate-in {
		animation: slide-in-from-top 0.3s ease-out;
	}
</style>
