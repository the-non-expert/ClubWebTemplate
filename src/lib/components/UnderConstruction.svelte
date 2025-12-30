<script lang="ts">
	interface Props {
		pageName: string;
	}

	let { pageName }: Props = $props();
</script>

<div class="min-h-[60vh] flex items-center justify-center py-16 md:py-24">
	<div class="container mx-auto px-4 sm:px-6 lg:px-8">
		<div class="max-w-2xl mx-auto text-center">
			<!-- Decorative top ornament -->
			<div class="flex items-center justify-center gap-3 mb-8">
				<div class="w-12 h-px bg-gradient-to-r from-transparent to-gold"></div>
				<div class="w-2 h-2 bg-gold rotate-45"></div>
				<div class="w-12 h-px bg-gradient-to-l from-transparent to-gold"></div>
			</div>

			<!-- Icon -->
			<div class="mb-8">
				<svg class="w-24 h-24 mx-auto text-gold/30" fill="none" stroke="currentColor" viewBox="0 0 24 24">
					<path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M19.428 15.428a2 2 0 00-1.022-.547l-2.387-.477a6 6 0 00-3.86.517l-.318.158a6 6 0 01-3.86.517L6.05 15.21a2 2 0 00-1.806.547M8 4h8l-1 1v5.172a2 2 0 00.586 1.414l5 5c1.26 1.26.367 3.414-1.415 3.414H4.828c-1.782 0-2.674-2.154-1.414-3.414l5-5A2 2 0 009 10.172V5L8 4z" />
				</svg>
			</div>

			<h1 class="font-serif text-4xl md:text-5xl font-bold text-primary mb-6">
				{pageName}
			</h1>

			<!-- Decorative divider -->
			<div class="flex items-center justify-center gap-3 mb-6">
				<div class="w-12 h-px bg-gradient-to-r from-transparent to-gold"></div>
				<div class="w-1.5 h-1.5 bg-gold rotate-45"></div>
				<div class="w-12 h-px bg-gradient-to-l from-transparent to-gold"></div>
			</div>

			<p class="text-gold text-sm tracking-[0.3em] uppercase mb-4 font-semibold">Under Construction</p>

			<p class="text-slate-600 text-lg leading-relaxed mb-8">
				We are currently refining this section to bring you the finest experience.
				Please check back soon or return to our homepage.
			</p>

			<div class="flex flex-col sm:flex-row gap-4 justify-center">
				<a
					href="/"
					class="inline-flex items-center justify-center gap-2 px-8 py-4 bg-primary text-white font-semibold tracking-wide hover:bg-primary/90 transition-all duration-300 hover:scale-105 group"
				>
					<svg class="w-5 h-5 group-hover:-translate-x-1 transition-transform" fill="none" stroke="currentColor" viewBox="0 0 24 24">
						<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 19l-7-7m0 0l7-7m-7 7h18" />
					</svg>
					<span>Return to Home</span>
				</a>
				<a
					href="/contact"
					class="inline-flex items-center justify-center gap-2 px-8 py-4 border-2 border-primary text-primary font-semibold tracking-wide hover:bg-primary hover:text-white transition-all duration-300 hover:scale-105"
				>
					<span>Contact Us</span>
				</a>
			</div>

			<!-- Decorative bottom ornament -->
			<div class="flex items-center justify-center gap-3 mt-12">
				<div class="w-12 h-px bg-gradient-to-r from-transparent to-gold"></div>
				<div class="w-2 h-2 bg-gold rotate-45"></div>
				<div class="w-12 h-px bg-gradient-to-l from-transparent to-gold"></div>
			</div>
		</div>
	</div>
</div>

<style>
	div {
		font-family: 'Crimson Text', serif;
	}

	h1 {
		font-family: 'Cormorant Garamond', serif;
	}
</style>
