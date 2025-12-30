<script lang="ts">
	interface Facility {
		title: string;
		description: string;
		image: string;
	}

	interface Room {
		title: string;
		description: string;
		price: string;
		features: string[];
		image: string;
	}

	interface Event {
		title: string;
		date: string;
		description: string;
		image: string;
	}

	const facilities: Facility[] = [
		{
			title: 'Heritage Library',
			description: 'An extensive collection of rare books and manuscripts in a refined reading room.',
			image: 'https://picsum.photos/seed/library/400/300'
		},
		{
			title: 'Sports Complex',
			description: 'State-of-the-art facilities for tennis, squash, badminton, and fitness.',
			image: 'https://picsum.photos/seed/sports/400/300'
		},
		{
			title: 'Fine Dining',
			description: 'Exquisite cuisine blending traditional and contemporary flavors.',
			image: 'https://picsum.photos/seed/dining/400/300'
		},
		{
			title: 'Members Bar',
			description: 'A sophisticated lounge offering premium spirits and craft cocktails.',
			image: 'https://picsum.photos/seed/bar/400/300'
		},
		{
			title: 'Conference Hall',
			description: 'Modern meeting spaces equipped with advanced technology.',
			image: 'https://picsum.photos/seed/conference/400/300'
		},
		{
			title: 'Grand Ballroom',
			description: 'An elegant venue for celebrations, galas, and special occasions.',
			image: 'https://picsum.photos/seed/ballroom/400/300'
		}
	];

	const rooms: Room[] = [
		{
			title: 'Deluxe Suite',
			description: 'Elegantly appointed rooms with classic furnishings and modern amenities.',
			price: '₹8,500',
			features: ['King Size Bed', 'En-suite Bathroom', 'City View', 'Complimentary Breakfast'],
			image: 'https://picsum.photos/seed/deluxe/500/350'
		},
		{
			title: 'Executive Suite',
			description: 'Spacious accommodations with separate living area and premium facilities.',
			price: '₹12,500',
			features: ['Master Bedroom', 'Living Room', 'Premium Bath', 'Club Access', 'Butler Service'],
			image: 'https://picsum.photos/seed/executive/500/350'
		},
		{
			title: 'Presidential Suite',
			description: 'The pinnacle of luxury with bespoke service and unparalleled comfort.',
			price: '₹25,000',
			features: ['2 Bedrooms', 'Dining Room', 'Private Terrace', 'Personal Concierge', 'Spa Access'],
			image: 'https://picsum.photos/seed/presidential/500/350'
		}
	];

	const events: Event[] = [
		{
			title: 'Annual Gala Dinner',
			date: 'December 31, 2025',
			description: 'Join us for an evening of elegance, fine dining, and celebration as we welcome the new year.',
			image: 'https://picsum.photos/seed/gala/400/300'
		},
		{
			title: 'Classical Music Concert',
			date: 'January 15, 2026',
			description: 'An enchanting evening featuring renowned classical musicians in our grand ballroom.',
			image: 'https://picsum.photos/seed/concert/400/300'
		},
		{
			title: 'Business Networking',
			date: 'January 28, 2026',
			description: 'Connect with distinguished professionals and leaders from various industries.',
			image: 'https://picsum.photos/seed/networking/400/300'
		}
	];

	let currentSlide = 0;
	const heroImages = [
		'https://picsum.photos/seed/hero1/1920/800',
		'https://picsum.photos/seed/hero2/1920/800',
		'https://picsum.photos/seed/hero3/1920/800'
	];

	// Auto-rotate hero images
	if (typeof window !== 'undefined') {
		setInterval(() => {
			currentSlide = (currentSlide + 1) % heroImages.length;
		}, 5000);
	}
</script>

<svelte:head>
	<title>Union Club - A Heritage of Excellence Since 1856</title>
	<meta name="description" content="Experience the finest traditions of hospitality and refinement at Union Club, Cuttack. Est. 1856." />
</svelte:head>

<!-- Hero Section -->
<section class="relative h-[600px] md:h-[700px] lg:h-[800px] overflow-hidden">
	<!-- Background Images with Parallax Effect -->
	<div class="absolute inset-0">
		{#each heroImages as image, i}
			<div
				class="absolute inset-0 transition-opacity duration-1000"
				class:opacity-100={i === currentSlide}
				class:opacity-0={i !== currentSlide}
			>
				<img
					src={image}
					alt="Union Club"
					class="w-full h-full object-cover"
				/>
				<div class="absolute inset-0 bg-gradient-to-b from-primary/60 via-primary/40 to-primary/70"></div>
			</div>
		{/each}
	</div>

	<!-- Content -->
	<div class="relative h-full flex items-center justify-center">
		<div class="text-center text-white px-4 max-w-4xl mx-auto">
			<!-- Decorative top ornament -->
			<div class="flex items-center justify-center gap-3 mb-8 animate-fade-in">
				<div class="w-12 h-px bg-gradient-to-r from-transparent to-gold"></div>
				<div class="w-2 h-2 bg-gold rotate-45"></div>
				<div class="w-12 h-px bg-gradient-to-l from-transparent to-gold"></div>
			</div>

			<h1 class="font-serif text-5xl md:text-6xl lg:text-7xl font-bold mb-6 animate-slide-up">
				Welcome to Union Club
			</h1>

			<p class="text-xl md:text-2xl mb-4 tracking-wide opacity-95 animate-slide-up" style="animation-delay: 0.2s;">
				A Heritage of Excellence Since 1856
			</p>

			<p class="text-base md:text-lg max-w-2xl mx-auto mb-8 leading-relaxed opacity-90 animate-slide-up" style="animation-delay: 0.4s;">
				Experience the timeless elegance of India's most prestigious heritage club,
				where tradition meets refined hospitality.
			</p>

			<!-- CTA Buttons -->
			<div class="flex flex-col sm:flex-row gap-4 justify-center animate-slide-up" style="animation-delay: 0.6s;">
				<a
					href="/membership"
					class="px-8 py-4 bg-gold text-primary font-semibold tracking-wide hover:bg-gold/90 transition-all duration-300 hover:scale-105 hover:shadow-2xl group relative overflow-hidden"
				>
					<span class="relative z-10">Become a Member</span>
					<div class="absolute inset-0 bg-white/10 scale-x-0 group-hover:scale-x-100 transition-transform origin-left"></div>
				</a>
				<a
					href="/about"
					class="px-8 py-4 border-2 border-white text-white font-semibold tracking-wide hover:bg-white hover:text-primary transition-all duration-300 hover:scale-105"
				>
					Discover Our Story
				</a>
			</div>

			<!-- Decorative bottom ornament -->
			<div class="flex items-center justify-center gap-3 mt-12 animate-fade-in" style="animation-delay: 0.8s;">
				<div class="w-12 h-px bg-gradient-to-r from-transparent to-gold"></div>
				<div class="w-2 h-2 bg-gold rotate-45"></div>
				<div class="w-12 h-px bg-gradient-to-l from-transparent to-gold"></div>
			</div>
		</div>
	</div>

	<!-- Slide Indicators -->
	<div class="absolute bottom-8 left-1/2 -translate-x-1/2 flex gap-2 z-10">
		{#each heroImages as _, i}
			<button
				class="h-2 rounded-full transition-all duration-300 {i === currentSlide ? 'w-8 bg-gold' : 'w-2 bg-white/50'}"
				on:click={() => currentSlide = i}
				aria-label={`Go to slide ${i + 1}`}
			></button>
		{/each}
	</div>
</section>

<!-- Welcome Section -->
<section class="py-16 md:py-24 bg-white">
	<div class="container mx-auto px-4 sm:px-6 lg:px-8">
		<div class="grid md:grid-cols-2 gap-12 lg:gap-16 items-center">
			<!-- Text Content -->
			<div class="order-2 md:order-1 space-y-6">
				<div>
					<p class="text-gold text-sm tracking-[0.3em] uppercase mb-3 font-semibold">Since 1856</p>
					<h2 class="font-serif text-4xl md:text-5xl font-bold text-primary mb-6">
						A Legacy of Distinction
					</h2>
					<div class="flex items-center gap-3 mb-6">
						<div class="w-12 h-px bg-gradient-to-r from-gold to-transparent"></div>
						<div class="w-1.5 h-1.5 bg-gold rotate-45"></div>
						<div class="w-12 h-px bg-gradient-to-l from-gold to-transparent"></div>
					</div>
				</div>

				<p class="text-slate-600 text-lg leading-relaxed">
					For nearly two centuries, Union Club has stood as a beacon of refinement and tradition
					in the heart of Cuttack. Our storied halls have witnessed generations of distinguished
					members, each contributing to the rich tapestry of our heritage.
				</p>

				<p class="text-slate-600 leading-relaxed">
					We offer an unparalleled sanctuary where timeless elegance meets contemporary comfort.
					From our meticulously curated facilities to our world-class dining experiences, every
					detail reflects our commitment to excellence.
				</p>

				<div class="grid grid-cols-3 gap-6 pt-6">
					<div class="text-center border-r border-amber-900/10 last:border-r-0">
						<p class="font-serif text-3xl font-bold text-gold mb-1">169</p>
						<p class="text-sm text-slate-500 uppercase tracking-wider">Years</p>
					</div>
					<div class="text-center border-r border-amber-900/10 last:border-r-0">
						<p class="font-serif text-3xl font-bold text-gold mb-1">2000+</p>
						<p class="text-sm text-slate-500 uppercase tracking-wider">Members</p>
					</div>
					<div class="text-center">
						<p class="font-serif text-3xl font-bold text-gold mb-1">50+</p>
						<p class="text-sm text-slate-500 uppercase tracking-wider">Events/Year</p>
					</div>
				</div>

				<a
					href="/about"
					class="inline-flex items-center gap-2 text-primary hover:text-gold font-semibold transition-colors group pt-4"
				>
					<span>Learn More About Us</span>
					<svg class="w-5 h-5 group-hover:translate-x-1 transition-transform" fill="none" stroke="currentColor" viewBox="0 0 24 24">
						<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 8l4 4m0 0l-4 4m4-4H3" />
					</svg>
				</a>
			</div>

			<!-- Image -->
			<div class="order-1 md:order-2 relative">
				<div class="relative overflow-hidden group">
					<img
						src="https://picsum.photos/seed/welcome/600/700"
						alt="Union Club Interior"
						class="w-full h-auto object-cover group-hover:scale-105 transition-transform duration-700"
					/>
					<div class="absolute inset-0 border-4 border-gold/20 pointer-events-none"></div>
					<!-- Decorative corner elements -->
					<div class="absolute top-0 left-0 w-12 h-12 border-t-2 border-l-2 border-gold"></div>
					<div class="absolute bottom-0 right-0 w-12 h-12 border-b-2 border-r-2 border-gold"></div>
				</div>
			</div>
		</div>
	</div>
</section>

<!-- Facilities Section -->
<section class="py-16 md:py-24 bg-gradient-to-b from-slate-50 to-white">
	<div class="container mx-auto px-4 sm:px-6 lg:px-8">
		<!-- Section Header -->
		<div class="text-center max-w-3xl mx-auto mb-12 lg:mb-16">
			<p class="text-gold text-sm tracking-[0.3em] uppercase mb-3 font-semibold">Our Amenities</p>
			<h2 class="font-serif text-4xl md:text-5xl font-bold text-primary mb-6">
				World-Class Facilities
			</h2>
			<div class="flex items-center justify-center gap-3 mb-6">
				<div class="w-12 h-px bg-gradient-to-r from-transparent to-gold"></div>
				<div class="w-1.5 h-1.5 bg-gold rotate-45"></div>
				<div class="w-12 h-px bg-gradient-to-l from-transparent to-gold"></div>
			</div>
			<p class="text-slate-600 text-lg">
				Experience excellence across every aspect of club life, from leisure to business.
			</p>
		</div>

		<!-- Facilities Grid -->
		<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
			{#each facilities as facility, i}
				<div
					class="group relative bg-white overflow-hidden hover:shadow-2xl transition-all duration-500 border border-amber-900/10 hover:border-gold/30"
					style="animation-delay: {i * 0.1}s;"
				>
					<!-- Image -->
					<div class="relative h-64 overflow-hidden">
						<img
							src={facility.image}
							alt={facility.title}
							class="w-full h-full object-cover group-hover:scale-110 transition-transform duration-700"
						/>
						<div class="absolute inset-0 bg-gradient-to-t from-primary/80 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-500"></div>
					</div>

					<!-- Content -->
					<div class="p-6 relative">
						<!-- Decorative corner -->
						<div class="absolute top-0 right-0 w-16 h-16 border-t border-r border-gold/20"></div>

						<h3 class="font-serif text-2xl font-bold text-primary mb-3 group-hover:text-gold transition-colors">
							{facility.title}
						</h3>
						<p class="text-slate-600 leading-relaxed">
							{facility.description}
						</p>

						<!-- Hover indicator -->
						<div class="absolute bottom-0 left-0 w-0 h-1 bg-gold group-hover:w-full transition-all duration-500"></div>
					</div>
				</div>
			{/each}
		</div>

		<div class="text-center mt-12">
			<a
				href="/facilities"
				class="inline-flex items-center gap-2 px-8 py-4 bg-primary text-white font-semibold tracking-wide hover:bg-primary/90 transition-all duration-300 hover:scale-105 group"
			>
				<span>Explore All Facilities</span>
				<svg class="w-5 h-5 group-hover:translate-x-1 transition-transform" fill="none" stroke="currentColor" viewBox="0 0 24 24">
					<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 8l4 4m0 0l-4 4m4-4H3" />
				</svg>
			</a>
		</div>
	</div>
</section>

<!-- Guest Rooms Section -->
<section class="py-16 md:py-24 bg-white">
	<div class="container mx-auto px-4 sm:px-6 lg:px-8">
		<!-- Section Header -->
		<div class="text-center max-w-3xl mx-auto mb-12 lg:mb-16">
			<p class="text-gold text-sm tracking-[0.3em] uppercase mb-3 font-semibold">Accommodations</p>
			<h2 class="font-serif text-4xl md:text-5xl font-bold text-primary mb-6">
				Luxury Guest Rooms
			</h2>
			<div class="flex items-center justify-center gap-3 mb-6">
				<div class="w-12 h-px bg-gradient-to-r from-transparent to-gold"></div>
				<div class="w-1.5 h-1.5 bg-gold rotate-45"></div>
				<div class="w-12 h-px bg-gradient-to-l from-transparent to-gold"></div>
			</div>
			<p class="text-slate-600 text-lg">
				Indulge in unparalleled comfort within our meticulously appointed suites.
			</p>
		</div>

		<!-- Rooms Grid -->
		<div class="grid grid-cols-1 lg:grid-cols-3 gap-8 lg:gap-10">
			{#each rooms as room, i}
				<div
					class="group relative bg-gradient-to-b from-white to-slate-50 overflow-hidden hover:shadow-2xl transition-all duration-500 border-2 border-amber-900/10 hover:border-gold/50"
					style="animation-delay: {i * 0.15}s;"
				>
					<!-- Image -->
					<div class="relative h-72 overflow-hidden">
						<img
							src={room.image}
							alt={room.title}
							class="w-full h-full object-cover group-hover:scale-110 transition-transform duration-700"
						/>
						<div class="absolute inset-0 bg-gradient-to-t from-primary to-transparent opacity-40"></div>

						<!-- Price Badge -->
						<div class="absolute top-4 right-4 bg-gold text-primary px-4 py-2 font-bold">
							<p class="text-xs uppercase tracking-wider mb-1">From</p>
							<p class="text-lg font-serif">{room.price}</p>
							<p class="text-xs opacity-75">per night</p>
						</div>
					</div>

					<!-- Content -->
					<div class="p-6">
						<h3 class="font-serif text-2xl font-bold text-primary mb-3 group-hover:text-gold transition-colors">
							{room.title}
						</h3>
						<p class="text-slate-600 mb-4 leading-relaxed">
							{room.description}
						</p>

						<!-- Features -->
						<ul class="space-y-2 mb-6">
							{#each room.features as feature}
								<li class="flex items-center gap-2 text-sm text-slate-600">
									<svg class="w-4 h-4 text-gold flex-shrink-0" fill="none" stroke="currentColor" viewBox="0 0 24 24">
										<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
									</svg>
									{feature}
								</li>
							{/each}
						</ul>

						<!-- CTA Button -->
						<a
							href="/rooms"
							class="block w-full text-center px-6 py-3 border-2 border-primary text-primary font-semibold hover:bg-primary hover:text-white transition-all duration-300 group-hover:border-gold group-hover:bg-gold group-hover:text-primary"
						>
							Book Now
						</a>
					</div>

					<!-- Decorative corners -->
					<div class="absolute top-0 left-0 w-8 h-8 border-t-2 border-l-2 border-gold opacity-0 group-hover:opacity-100 transition-opacity"></div>
					<div class="absolute bottom-0 right-0 w-8 h-8 border-b-2 border-r-2 border-gold opacity-0 group-hover:opacity-100 transition-opacity"></div>
				</div>
			{/each}
		</div>
	</div>
</section>

<!-- Events Section -->
<section class="py-16 md:py-24 bg-gradient-to-b from-slate-50 to-white">
	<div class="container mx-auto px-4 sm:px-6 lg:px-8">
		<!-- Section Header -->
		<div class="text-center max-w-3xl mx-auto mb-12 lg:mb-16">
			<p class="text-gold text-sm tracking-[0.3em] uppercase mb-3 font-semibold">Upcoming</p>
			<h2 class="font-serif text-4xl md:text-5xl font-bold text-primary mb-6">
				Club Events
			</h2>
			<div class="flex items-center justify-center gap-3 mb-6">
				<div class="w-12 h-px bg-gradient-to-r from-transparent to-gold"></div>
				<div class="w-1.5 h-1.5 bg-gold rotate-45"></div>
				<div class="w-12 h-px bg-gradient-to-l from-transparent to-gold"></div>
			</div>
			<p class="text-slate-600 text-lg">
				Join us for exclusive gatherings, cultural celebrations, and networking opportunities.
			</p>
		</div>

		<!-- Events Grid -->
		<div class="grid grid-cols-1 md:grid-cols-3 gap-8">
			{#each events as event, i}
				<div
					class="group bg-white overflow-hidden hover:shadow-2xl transition-all duration-500 border border-amber-900/10 hover:border-gold/30"
					style="animation-delay: {i * 0.1}s;"
				>
					<!-- Image -->
					<div class="relative h-56 overflow-hidden">
						<img
							src={event.image}
							alt={event.title}
							class="w-full h-full object-cover group-hover:scale-110 transition-transform duration-700"
						/>
						<div class="absolute inset-0 bg-primary/20 group-hover:bg-primary/40 transition-colors"></div>

						<!-- Date Badge -->
						<div class="absolute top-4 left-4 bg-white/95 backdrop-blur-sm px-4 py-3 text-center">
							<p class="text-2xl font-serif font-bold text-gold">{event.date.split(' ')[1].replace(',', '')}</p>
							<p class="text-xs uppercase tracking-wider text-primary font-semibold">{event.date.split(' ')[0]}</p>
						</div>
					</div>

					<!-- Content -->
					<div class="p-6">
						<h3 class="font-serif text-xl font-bold text-primary mb-2 group-hover:text-gold transition-colors">
							{event.title}
						</h3>
						<p class="text-sm text-slate-500 mb-3 flex items-center gap-2">
							<svg class="w-4 h-4 text-gold" fill="none" stroke="currentColor" viewBox="0 0 24 24">
								<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8 7V3m8 4V3m-9 8h10M5 21h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v12a2 2 0 002 2z" />
							</svg>
							{event.date}
						</p>
						<p class="text-slate-600 leading-relaxed mb-4">
							{event.description}
						</p>
						<a
							href="/events"
							class="inline-flex items-center gap-2 text-primary hover:text-gold font-semibold transition-colors group/link"
						>
							<span>Learn More</span>
							<svg class="w-4 h-4 group-hover/link:translate-x-1 transition-transform" fill="none" stroke="currentColor" viewBox="0 0 24 24">
								<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 8l4 4m0 0l-4 4m4-4H3" />
							</svg>
						</a>
					</div>
				</div>
			{/each}
		</div>

		<div class="text-center mt-12">
			<a
				href="/events"
				class="inline-flex items-center gap-2 px-8 py-4 border-2 border-primary text-primary font-semibold tracking-wide hover:bg-primary hover:text-white transition-all duration-300 hover:scale-105 group"
			>
				<span>View All Events</span>
				<svg class="w-5 h-5 group-hover:translate-x-1 transition-transform" fill="none" stroke="currentColor" viewBox="0 0 24 24">
					<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8 7V3m8 4V3m-9 8h10M5 21h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v12a2 2 0 002 2z" />
				</svg>
			</a>
		</div>
	</div>
</section>

<!-- Call to Action Section -->
<section class="py-16 md:py-24 bg-gradient-to-br from-primary via-primary to-slate-900 text-white relative overflow-hidden">
	<!-- Decorative background pattern -->
	<div class="absolute inset-0 opacity-5">
		<div class="absolute inset-0" style="background-image: repeating-linear-gradient(45deg, transparent, transparent 35px, rgba(255,255,255,.1) 35px, rgba(255,255,255,.1) 70px);"></div>
	</div>

	<div class="container mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
		<div class="max-w-3xl mx-auto text-center">
			<div class="flex items-center justify-center gap-3 mb-6">
				<div class="w-12 h-px bg-gradient-to-r from-transparent to-gold"></div>
				<div class="w-2 h-2 bg-gold rotate-45"></div>
				<div class="w-12 h-px bg-gradient-to-l from-transparent to-gold"></div>
			</div>

			<h2 class="font-serif text-4xl md:text-5xl font-bold mb-6">
				Join Our Distinguished Community
			</h2>
			<p class="text-xl mb-8 leading-relaxed opacity-95">
				Become part of a legacy that spans nearly two centuries. Experience the prestige,
				privilege, and refined lifestyle that only Union Club can offer.
			</p>

			<div class="flex flex-col sm:flex-row gap-4 justify-center">
				<a
					href="/membership"
					class="px-8 py-4 bg-gold text-primary font-bold tracking-wide hover:bg-gold/90 transition-all duration-300 hover:scale-105 hover:shadow-2xl"
				>
					Apply for Membership
				</a>
				<a
					href="/contact"
					class="px-8 py-4 border-2 border-white text-white font-semibold tracking-wide hover:bg-white hover:text-primary transition-all duration-300 hover:scale-105"
				>
					Contact Us
				</a>
			</div>

			<div class="flex items-center justify-center gap-3 mt-8">
				<div class="w-12 h-px bg-gradient-to-r from-transparent to-gold"></div>
				<div class="w-2 h-2 bg-gold rotate-45"></div>
				<div class="w-12 h-px bg-gradient-to-l from-transparent to-gold"></div>
			</div>
		</div>
	</div>
</section>

<style>
	@keyframes fade-in {
		from {
			opacity: 0;
		}
		to {
			opacity: 1;
		}
	}

	@keyframes slide-up {
		from {
			opacity: 0;
			transform: translateY(30px);
		}
		to {
			opacity: 1;
			transform: translateY(0);
		}
	}

	.animate-fade-in {
		animation: fade-in 1s ease-out;
	}

	.animate-slide-up {
		animation: slide-up 0.8s ease-out;
		animation-fill-mode: both;
	}

	section {
		font-family: 'Crimson Text', serif;
	}

	h1, h2, h3 {
		font-family: 'Cormorant Garamond', serif;
	}
</style>
