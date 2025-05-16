<script lang="ts">
	// Sample data - replace with your actual data
	const home = {
		title: 'Welcome to Brisk Solutions',
		button_text: 'Get Started',
		button_link: '/contact',
		link_one_text: 'Our Services',
		link_one: '/services',
		link_two_text: 'Our Process',
		link_two: '/process',
		image: '/heroBg.jpg', // Replace with your hero image
		full_screen_image: '/images/fullscreen.jpg', // Replace with your full screen image
		cta_title: 'Transforming Ideas into Digital Reality',
		cta_description: "We help businesses leverage technology to grow and succeed in today's digital world.",
		footer_cta_title: 'Ready to Start Your Project?',
		footer_cta_description: "Let's create something amazing together!",
		footer_cta_button_text: 'Contact Us Today',
		footer_cta_button_link: '/contact',
		footer_cta_image: '/computerOpen.jpg' // Replace with your footer image
	};

	// Sample blog posts - replace with your actual data
	const blogs = [
		{
			url: '/blog/post-1',
			image: '/briskhr.png',
			title: 'BRISK HR',
			description:
				'Brisk HR is a comprehensive human resource management system that enables the tracking, management , and analysis of all the employees from recruitment to separation.'
		},
		{
			url: '/blog/post-2',
			image: '/brisksaas.png',
			title: 'BRISK SAAS',
			description:
				'Brisk SAAS is a hosting model for Brisk Enterprise Resource Planning(ERP) software which involves the software applications on our cloud servers.The goal of SAAS ERP hosting is to reduce costs in software,hardware and support.'
		},
		{
			url: '/blog/post-2',
			image: '/brisksaltrack1.png',
			title: 'BRISK SALTRACK',
			description:
				'Brisk SalTrak is a business tool that SalTrak focusses on simplifying an FMCG distributors business processes in field sales and reporting. Essentially built for organisations that focus on distribution, the solution provides real time and accurate information that facilitates proper planning and decision making.',
			features: ['Features', 'Tracking and Monitoring', 'Improved Sales Reps Reporting Time', 'Route Optimization']
		},
		{
			url: '/blog/post-2',
			image: '/briskEnvi.png',
			title: 'BRISK ENVI',
			description:
				'Brisk e-nvironment seeks to contribute to the achievement of three Millenium Development Goals : eradicating extreme poverty and hunger, promoting gender equality and empower women, and ensure environmental sustainability. Brisk is contributing to the MDGs through provision and implementation of Brisk e-nvironment, a dynamic integrated environment Management sytem, customized for a wide range of institutions and organizations with an aim of helping them improve their performance and save resources.'
		},
		{
			url: '/blog/post-2',
			image: '/briskerp.png',
			title: 'BRISK ERP',
			description:
				'Brisk ERP provides an integrated real-time view of core business processes, using common databases maintained by a database management system. Brisk ERP system tracks business resources - cash,raw materials,production capacity - and the status of the business commitments: orders, purchase orders and payroll.',
			features: [
				'Fully Customizable',
				'Flexible Platform',
				'Mobile/Browser Access',
				'Platform Independet',
				'Flexible Import and Export',
				'Integrated Report Writer',
				'Secure, Role Based Access and Logging',
				'Multiple User Interfaces & Accounts'
			]
		},
		{
			url: '/blog/post-2',
			image: '/brisk-biometricks.png',
			title: 'BRISK BIOMETRIC',
			description:
				'Brisk BioMetric is a registration and verification solution. It incorporates finger print and photo recognition. Accessible to management anywhere using internet connection.'
		}
	];

	// Sample categories - replace with your actual data
	const categories = [
		{
			url: '/#',
			title: 'Web Development',
			image: '/webCode.jpg'
		},
		{
			url: '/#',
			title: 'Mobile Apps',
			image: '/mobile.jpg'
		},
		{
			url: '/#',
			title: 'Cloud Solutions',
			image: '/servers.jpg'
		}
	];

	const otherServices = {
		title: 'OTHER SERVICES',
		description: 'We also offer deployment and integration of Automated Material Handling Systems/Solutions (AMHS) such as:',
		features: ['Process Weighers', 'Cereal & Milling machines among others'],
		buttonText: 'LEARN MORE',
		buttonLink: '/services/amhs',
		image: '/grainmachines.jpg' // Replace with your actual image path
	};
</script>

<div class="bg-primary relative h-screen w-full px-12 py-12">
	<div class="relative z-10 py-24 text-center md:py-48">
		<h1 class="font-display mb-12 text-center text-3xl font-bold text-white md:text-4xl lg:text-5xl xl:text-6xl">
			{home.title}
		</h1>
		<h5 class="font-display mb-6 text-center text-lg font-light text-white md:text-xl lg:text-2xl xl:text-3xl">
			Proficiency in Business Processes Automation
		</h5>
		<a href={home.button_link} class="font-heading inline-block bg-[#3a4f9b] px-8 py-4 text-sm tracking-widest text-white uppercase"
			>{home.button_text}</a
		>
	</div>

	<div class="font-heading relative z-10 mx-auto flex max-w-4xl justify-between text-sm tracking-widest text-white uppercase">
		<a href={home.link_one} class="border-b border-white">{home.link_one_text}</a>
		<a href={home.link_two} class="border-b border-white">{home.link_two_text}</a>
	</div>

	<img src={home.image} class="absolute inset-0 h-full w-full object-cover opacity-60" alt="Hero background" />
</div>

<!-- Services Section Header -->
<div class="container mx-auto px-4 py-8">
	<div class="border-primary mb-2 inline-block w-24 border-b-3 tracking-wider text-gray-500 uppercase">SERVICES</div>
	<h2 class=" mb-12 text-3xl font-bold text-gray-800 md:text-4xl lg:text-5xl">WHAT WE OFFER..</h2>
</div>

{#each blogs as blog, i}
	<div class="mb-12 grid grid-cols-1 md:grid-cols-2">
		{#if i % 2 === 0}
			<!-- Image left, text right -->
			<div class="flex items-center justify-end bg-white p-12 md:p-24">
				<a href={blog.url}>
					<img src={blog.image} class="w-full max-w-md" alt={blog.title} />
				</a>
			</div>
			<div class="flex items-center justify-start bg-gray-100 p-12 md:p-24">
				<div class="max-w-md">
					<div class="bg-primary mb-4 h-2 w-24"></div>
					<h2 class="font-display mb-6 text-2xl font-bold md:text-3xl lg:text-4xl">
						{blog.title}
					</h2>
					<p class="mb-6 text-sm leading-relaxed font-light text-gray-600 md:text-base">
						{blog.description}
					</p>
					{#if blog.features}
						<ul class="mb-6 list-inside list-disc text-sm text-gray-700">
							{#each blog.features as feature}
								<li>{feature}</li>
							{/each}
						</ul>
					{/if}
					<a
						href={blog.url}
						class="hover:bg-primary inline-block border-2 border-[#5069c3] px-8 py-3 text-sm font-light tracking-widest text-[#5069c3] uppercase hover:text-white"
						>Read more
					</a>
				</div>
			</div>
		{:else}
			<!-- Text left, image right -->
			<div class="flex items-center justify-start bg-gray-100 p-12 md:p-24">
				<div class="max-w-md">
					<div class="bg-primary mb-4 h-2 w-24"></div>
					<h2 class="font-display mb-6 text-2xl font-bold md:text-3xl lg:text-4xl">
						{blog.title}
					</h2>
					<p class="mb-6 text-sm leading-relaxed font-light text-gray-600 md:text-base">
						{blog.description}
					</p>
					{#if blog.features}
						<ul class="mb-6 list-inside list-disc text-sm text-gray-700">
							{#each blog.features as feature}
								<li>{feature}</li>
							{/each}
						</ul>
					{/if}
					<a
						href={blog.url}
						class="hover:bg-primary inline-block border-2 border-[#5069c3] px-8 py-3 text-sm font-light tracking-widest text-[#5069c3] uppercase hover:text-white"
					>
						Read more
					</a>
				</div>
			</div>
			<div class="flex items-center justify-end bg-white p-12 md:p-24">
				<a href={blog.url}>
					<img src={blog.image} class="w-full max-w-md" alt={blog.title} />
				</a>
			</div>
		{/if}
	</div>
{/each}

<!-- Other Services Section -->
<div class="container mx-auto px-4 py-16 md:py-24">
	<div class="">
		<div class="border-primary mb-2 inline-block w-35 border-b-3 tracking-wider text-gray-500 uppercase">{otherServices.title}</div>
		<div class="grid grid-cols-1 items-center gap-8 md:grid-cols-2">
			<div>
				<h3 class="mb-6 text-2xl text-gray-800">
					{otherServices.description}
				</h3>

				<ul class="mb-8 list-disc pl-5">
					{#each otherServices.features as feature}
						<li class="mb-3 text-lg text-gray-700">{feature}</li>
					{/each}
				</ul>

				<a
					href={otherServices.buttonLink}
					class="inline-block bg-blue-700 px-8 py-3 font-bold tracking-widest text-white uppercase hover:bg-blue-800"
				>
					{otherServices.buttonText}
				</a>
			</div>
			<div class="flex justify-center">
				<img src={otherServices.image} alt="Automated Material Handling Systems" class="w-full max-w-md" />
			</div>
		</div>
	</div>
</div>

<!-- {#if home.full_screen_image}
	<img src={home.full_screen_image} class="h-screen w-full object-cover" alt="Full screen showcase" />
{/if}

{#if home.cta_title}
	<div class="mx-auto max-w-xl py-24 text-center md:py-32">
		<div class="bg-primary mx-auto mb-4 h-2 w-24"></div>
		<h2 class="font-display mb-6 text-3xl font-bold md:text-4xl lg:text-5xl">{home.cta_title}</h2>
		<p class="mb-6 leading-relaxed font-light text-gray-600">{home.cta_description}</p>
	</div>
{/if} -->

<div class="flex flex-wrap bg-black">
	{#each categories.slice(0, 3) as category}
		<a
			href={category.url}
			class="font-heading relative flex h-72 w-full items-center justify-center bg-black tracking-widest text-white uppercase hover:opacity-75 md:w-auto md:flex-1"
		>
			<div class="relative z-10">{category.title}</div>
			<img src={category.image} class="absolute inset-0 h-full w-full object-cover opacity-50" alt={category.title} />
		</a>
	{/each}
</div>

{#if blogs.length > 1}
	<div class="grid grid-cols-1 md:grid-cols-2">
		<div class="flex items-center justify-start bg-white p-12 md:p-24">
			<a href={blogs[1].url}>
				<img src={blogs[1].image} class="w-full max-w-md" alt={blogs[1].title} />
			</a>
		</div>

		<div class="flex items-center justify-end bg-gray-100 p-12 md:order-first md:p-24">
			<div class="max-w-md">
				<div class="bg-primary mb-4 h-2 w-24"></div>
				<h2 class="font-display mb-6 text-2xl font-bold md:text-3xl lg:text-4xl">
					{blogs[1].title}
				</h2>
				<p class="mb-6 text-sm leading-relaxed font-light text-gray-600 md:text-base">
					{blogs[1].description}
				</p>
				<a
					href={blogs[1].url}
					class="hover:bg-primary inline-block border-2 border-[#5069c3] px-8 py-3 text-sm font-light tracking-widest text-[#5069c3] uppercase hover:text-white"
					>Read more
				</a>
			</div>
		</div>
	</div>
{/if}

{#if home.footer_cta_image}
	<div class="relative w-full px-12 py-12">
		<div class="relative z-10 py-12 text-center md:py-24">
			<h1 class="font-display mb-6 text-center text-3xl font-bold tracking-tighter text-white md:text-4xl lg:text-5xl xl:text-6xl">
				{home.footer_cta_title}
			</h1>
			<p class="mb-10 text-base font-bold text-white md:text-lg">{home.footer_cta_description}</p>
			<a
				href={home.footer_cta_button_link}
				class="font-heading inline-block bg-[#3a4f9b] px-8 py-4 text-sm tracking-widest text-white uppercase"
				>{home.footer_cta_button_text}
			</a>
		</div>

		<img src={home.footer_cta_image} class="absolute inset-0 h-full w-full object-cover" alt="Footer CTA background" />
	</div>
{/if}

<!-- Where to Find Us - Map Section -->
<div class="bg-gray-50 py-16 md:py-24">
	<div class="container mx-auto px-4">
		<div class="mb-12 text-center">
			<h2 class="text-3xl font-bold text-gray-800 md:text-4xl">Where to Find Us</h2>
			<p class="mt-2 text-gray-600">Visit our location at La Foret Conference Centre.</p>
		</div>
		<div class="relative h-96 w-full overflow-hidden rounded-lg shadow-xl md:h-[500px]">
			<iframe
				src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3988.851757999198!2d36.80280867496561!3d-1.265014498728368!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x182f1741713610c1%3A0x50a21b4b1a3979a8!2sLa%20Foret%20Conference%20Centre!5e0!3m2!1sen!2ske!4v1714901000000!5m2!1sen!2ske"
				width="100%"
				height="100%"
				style="border:0;"
				allowfullscreen
				loading="lazy"
				referrerpolicy="no-referrer-when-downgrade"
				title="La Foret Conference Centre Location"
			></iframe>
		</div>
	</div>
</div>

<!-- About Section CTA -->
<div class="container mx-auto px-4 py-16 md:py-24">
	<div class="text-center">
		<h2 class="mb-6 text-3xl font-bold text-gray-800 md:text-4xl lg:text-5xl">Learn More About Us</h2>
		<p class="mx-auto mb-8 max-w-2xl text-lg text-gray-600">
			Discover our story, mission, vision, and the values that drive us to deliver exceptional software solutions.
		</p>
		<a href="/about" class="bg-primary hover:bg-primary/90 inline-block rounded px-8 py-4 font-medium text-white transition-all">
			Visit Our About Page
		</a>
	</div>
</div>
