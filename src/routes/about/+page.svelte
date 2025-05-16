<script lang="ts">
	// About Us Page Content
	const about = {
		title: 'WHO WE ARE..',
		subtitle: 'ABOUT US',
		description: [
			'Brisk Solution Company limited (BSL). BSL is a Software Engineering and Development enterprise founded in Kenya. We are focused on proficiency in business processes automation by providing our clients with enterprise software solutions based on Open-Source technologies and excellent industry standards.',
			'Our emphasis is on improving the quality of decisions made for the business, planning with strategic execution to improve investment returns for our clients.',
			'BSL strives to become the preferred industry standard for the provision of software solutions that are functional, maintainable, dependable, efficient and that perform to specific requirements. These has involved developing software components and applications for the both desktop and mobile'
		],
		image: '/brisklogo.jpg'
	};

	const companyValues = {
		subtitle: 'MISSION & VISION',
		title: 'WHAT DRIVES US..',
		mission: {
			title: 'Mission',
			description: 'To be the preferred Business Software Automation and Consulting House in the region.',
			icon: 'bi-rocket-takeoff-fill'
		},
		vision: {
			title: 'Vision',
			description: 'To deliver products and services of superior quality that meets the unique needs and expectations of each client.',
			icon: 'bi-eye-fill'
		},
		coreValues: {
			title: 'Core Values',
			values: ['Relationships', 'Innovation', 'Financial Responsibility', 'Integrity'],
			icon: 'bi-award-fill'
		}
	};

	const team = {
		title: 'OUR TEAM',
		subtitle: 'THE PEOPLE BEHIND BRISK',
		description: 'Our team of experienced professionals is dedicated to providing excellent solutions that meet your unique needs.',
		members: [
			{
				name: 'John Kamau',
				position: 'CEO & Founder',
				bio: 'With over 15 years of experience in software development and business strategy, John leads our team with vision and expertise.',
				image: '/images/team/john.jpg'
			},
			{
				name: 'Sarah Njeri',
				position: 'Lead Developer',
				bio: 'Sarah specializes in creating robust and scalable software solutions with the latest technologies.',
				image: '/images/team/sarah.jpg'
			},
			{
				name: 'David Mwangi',
				position: 'Project Manager',
				bio: 'David ensures all projects are delivered on time and to the highest standards of quality.',
				image: '/images/team/david.jpg'
			}
		]
	};

	const timeline = {
		title: 'OUR JOURNEY',
		subtitle: 'MILESTONES',
		events: [
			{
				year: '2010',
				title: 'Foundation',
				description: 'Brisk Solutions was founded with a vision to transform business processes through technology.'
			},
			{
				year: '2013',
				title: 'First Major Project',
				description: 'Successfully completed our first enterprise-level ERP implementation.'
			},
			{
				year: '2016',
				title: 'Expansion',
				description: 'Expanded our team and service offerings to include mobile application development.'
			},
			{
				year: '2020',
				title: 'Innovation Award',
				description: 'Recognized for innovation in business process automation solutions.'
			},
			{
				year: '2023',
				title: 'Regional Growth',
				description: 'Extended operations to serve clients across East Africa.'
			}
		]
	};

	const clients = {
		title: 'TRUSTED BY',
		subtitle: 'OUR CLIENTS',
		logos: [
			{ name: 'Company A', logo: '/images/clients/client1.png' },
			{ name: 'Company B', logo: '/images/clients/client2.png' },
			{ name: 'Company C', logo: '/images/clients/client3.png' },
			{ name: 'Company D', logo: '/images/clients/client4.png' },
			{ name: 'Company E', logo: '/images/clients/client5.png' }
		]
	};

	const testimonials = {
		title: 'WHAT PEOPLE SAY',
		subtitle: 'TESTIMONIALS',
		quotes: [
			{
				text: 'Unique themes, unique service- Brisk does not only produce a wonderful product but also guide you through making the product work for you!',
				author: 'Ryan Munene',
				company: 'Satisfied Client'
			},
			{
				text: 'The team at Brisk is professional, responsive, and truly understands our business needs. Highly recommended!',
				author: 'John Smith',
				company: 'XYZ Logistics'
			},
			{
				text: 'Their innovative approach to software development has given us a competitive edge in our industry.',
				author: 'Mary Johnson',
				company: 'Global Retailers Ltd'
			}
		]
	};

	const contactInfo = {
		address: {
			line1: 'Steward House, Jamhuri Park Showground',
			line2: 'Off Ngong Road, Nairobi'
		},
		phone: '+254 786 926 142',
		email: 'info@bsl.co.ke',
		postal: 'P.O. Box 13338 – 00200, Nairobi'
	};
</script>

<!-- Hero Section -->
<div class="relative bg-gradient-to-r from-blue-800 to-indigo-900 py-24 md:py-32">
	<div class="absolute inset-0 opacity-20">
		<div class="h-full w-full bg-[url('/heroBg.jpg')] bg-cover bg-center"></div>
	</div>
	<div class="relative container mx-auto px-4 text-center">
		<h1 class="mb-4 text-4xl font-bold tracking-tight text-white md:text-5xl lg:text-6xl">About Brisk Solutions</h1>
		<p class="mx-auto mt-6 max-w-2xl text-xl font-light text-white/90">
			Software Engineering and Development enterprise focused on business processes automation through enterprise solutions based on
			Open-Source technologies.
		</p>
	</div>
</div>

<!-- Main About Section -->
<div class="container mx-auto px-4 py-16 md:py-24">
	<div class="grid grid-cols-1 items-center gap-12 md:grid-cols-2">
		<div class="order-2 md:order-1">
			<div class="border-primary mb-2 inline-block w-24 border-b-2 tracking-wider text-gray-500 uppercase">{about.subtitle}</div>
			<h2 class="mb-8 text-3xl font-bold text-gray-800 md:text-4xl lg:text-5xl">{about.title}</h2>

			{#each about.description as paragraph}
				<p class="mb-6 text-justify text-lg leading-relaxed text-gray-700">{paragraph}</p>
			{/each}

			<!-- Call to Action Button -->
			<div class="mt-8">
				<a href="/contact" class="bg-primary hover:bg-primary/90 inline-block rounded px-8 py-4 font-medium text-white transition-all">
					Get in Touch
				</a>
			</div>
		</div>
		<div class="order-1 flex justify-center md:order-2">
			<div class="relative">
				<div class="bg-primary/20 absolute -top-6 -left-6 h-24 w-24 rounded-lg"></div>
				<img src={about.image} alt="Brisk Solutions Logo" class="relative z-10 w-full max-w-md rounded shadow-xl" />
				<div class="bg-primary/20 absolute -right-6 -bottom-6 h-24 w-24 rounded-lg"></div>
			</div>
		</div>
	</div>
</div>

<!-- Mission Vision Values Section -->
<div class="bg-gray-50 py-16 md:py-24">
	<div class="container mx-auto px-4">
		<div class="mb-16 text-center">
			<div class="border-primary mx-auto mb-2 inline-block w-48 border-b-2 tracking-wider text-gray-500 uppercase">
				{companyValues.subtitle}
			</div>
			<h2 class="mb-8 text-3xl font-bold text-gray-800 md:text-4xl lg:text-5xl">{companyValues.title}</h2>
		</div>

		<div class="grid grid-cols-1 gap-10 md:grid-cols-3">
			<!-- Mission Card -->
			<div class="group rounded-lg bg-white p-8 shadow-lg transition-all hover:shadow-xl">
				<div class="mb-6 flex justify-center">
					<span class="bg-primary/10 text-primary group-hover:bg-primary rounded-full p-6 transition-all group-hover:text-white">
						<i class="{companyValues.mission.icon} text-4xl"></i>
					</span>
				</div>
				<h3 class="mb-4 text-center text-2xl font-bold">{companyValues.mission.title}</h3>
				<p class="text-center text-lg leading-relaxed text-gray-600">
					{companyValues.mission.description}
				</p>
			</div>

			<!-- Vision Card -->
			<div class="group rounded-lg bg-white p-8 shadow-lg transition-all hover:shadow-xl">
				<div class="mb-6 flex justify-center">
					<span class="bg-primary/10 text-primary group-hover:bg-primary rounded-full p-6 transition-all group-hover:text-white">
						<i class="{companyValues.vision.icon} text-4xl"></i>
					</span>
				</div>
				<h3 class="mb-4 text-center text-2xl font-bold">{companyValues.vision.title}</h3>
				<p class="text-center text-lg leading-relaxed text-gray-600">
					{companyValues.vision.description}
				</p>
			</div>

			<!-- Core Values Card -->
			<div class="group rounded-lg bg-white p-8 shadow-lg transition-all hover:shadow-xl">
				<div class="mb-6 flex justify-center">
					<span class="bg-primary/10 text-primary group-hover:bg-primary rounded-full p-6 transition-all group-hover:text-white">
						<i class="{companyValues.coreValues.icon} text-4xl"></i>
					</span>
				</div>
				<h3 class="mb-4 text-center text-2xl font-bold">{companyValues.coreValues.title}</h3>
				<div class="flex justify-center">
					<ul class="mx-auto space-y-3 text-lg">
						{#each companyValues.coreValues.values as value}
							<li class="flex items-center text-gray-600">
								<i class="bi-check-circle-fill text-primary mr-3"></i>
								<span class="text-gray-600">{value}</span>
							</li>
						{/each}
					</ul>
				</div>
			</div>
		</div>
	</div>
</div>

<!-- Timeline Section -->
<!-- <div class="container mx-auto px-4 py-16 md:py-24">
	<div class="mb-16 text-center">
		<div class="border-primary mx-auto mb-2 inline-block w-32 border-b-2 tracking-wider text-gray-500 uppercase">{timeline.subtitle}</div>
		<h2 class="mb-8 text-3xl font-bold text-gray-800 md:text-4xl">{timeline.title}</h2>
	</div>

	<div class="relative">
		<!-- Timeline Line --
		<div class="bg-primary/20 absolute top-0 left-0 h-full w-1 -translate-x-1/2 md:left-1/2"></div>

		<!-- Timeline Events --
		<div class="space-y-12">
			{#each timeline.events as event, i}
				<div class="relative flex flex-col md:flex-row {i % 2 === 0 ? 'md:flex-row-reverse' : ''}">
					<div class="flex md:w-1/2 {i % 2 === 0 ? 'md:justify-start' : 'md:justify-end'} mb-8 md:mb-0">
						<div class="relative w-full max-w-md {i % 2 === 0 ? 'md:ml-12' : 'md:mr-12'} rounded-lg bg-white p-6 shadow-lg">
							<div
								class="absolute top-6 {i % 2 === 0
									? 'left-[-36px] md:left-[-36px]'
									: 'left-[-36px] md:right-[-36px] md:left-auto'} bg-primary flex h-8 w-8 items-center justify-center rounded-full"
							>
								<div class="h-3 w-3 rounded-full bg-white"></div>
							</div>
							<span class="text-primary text-xl font-bold">{event.year}</span>
							<h3 class="mt-2 text-xl font-bold">{event.title}</h3>
							<p class="mt-2 text-gray-600">{event.description}</p>
						</div>
					</div>
					<div class="md:w-1/2"></div>
				</div>
			{/each}
		</div>
	</div>
</div> -->

<!-- Team Section
<div class="bg-gray-50 py-16 md:py-24">
	<div class="container mx-auto px-4">
		<div class="mb-16 text-center">
			<div class="border-primary mx-auto mb-2 inline-block w-32 border-b-2 tracking-wider text-gray-500 uppercase">{team.subtitle}</div>
			<h2 class="mb-4 text-3xl font-bold text-gray-800 md:text-4xl">{team.title}</h2>
			<p class="mx-auto max-w-2xl text-lg text-gray-600">{team.description}</p>
		</div>

		<div class="grid grid-cols-1 gap-8 sm:grid-cols-2 lg:grid-cols-3">
			{#each team.members as member}
				<div class="group overflow-hidden rounded-lg bg-white shadow-lg transition-all hover:shadow-xl">
					<div class="relative h-64 overflow-hidden">
						<div class="bg-primary/60 absolute inset-0 opacity-0 transition-opacity duration-300 group-hover:opacity-100"></div>
						<div class="absolute inset-0 bg-gradient-to-t from-black/70 to-transparent"></div>

						<!-- If we have member images, use them, otherwise use a placeholder --
						<div class="h-full w-full bg-gray-300">
							<!--<img src={member.image} alt={member.name} class="h-full w-full object-cover" />--
						</div>

						<div class="absolute bottom-0 left-0 w-full p-4">
							<h3 class="text-xl font-bold text-white">{member.name}</h3>
							<p class="text-white/90">{member.position}</p>
						</div>
					</div>
					<div class="p-6">
						<p class="text-gray-600">{member.bio}</p>
					</div>
				</div>
			{/each}
		</div>
	</div>
</div> -->

<!-- Testimonials Section -->
<div class="container mx-auto px-4 py-16 md:py-24">
	<div class="mb-16 text-center">
		<div class="border-primary mx-auto mb-2 inline-block w-36 border-b-2 tracking-wider text-gray-500 uppercase">
			{testimonials.subtitle}
		</div>
		<h2 class="mb-4 text-3xl font-bold text-gray-800 md:text-4xl">{testimonials.title}</h2>
	</div>

	<div class="grid grid-cols-1 gap-8 md:grid-cols-3">
		{#each testimonials.quotes as quote}
			<div class="rounded-lg bg-white p-8 shadow-lg">
				<div class="text-primary/20 mb-4 text-5xl">"</div>
				<p class="mb-6 text-lg text-gray-700 italic">{quote.text}</p>
				<div class="flex items-center">
					<div class="h-12 w-12 rounded-full bg-gray-300"></div>
					<div class="ml-4">
						<h4 class="font-bold">{quote.author}</h4>
						<p class="text-sm text-gray-600">{quote.company}</p>
					</div>
				</div>
			</div>
		{/each}
	</div>
</div>

<!-- Contact CTA Section -->
<div class="bg-primary py-16 text-center md:py-24">
	<div class="container mx-auto px-4">
		<h2 class="mb-6 text-3xl font-bold text-white md:text-4xl">Ready to work with us?</h2>
		<p class="mx-auto mb-10 max-w-2xl text-lg text-white/90">
			Contact our team today to discuss how we can help your business succeed with our software solutions.
		</p>
		<a href="/contact" class="text-primary inline-block rounded-md bg-white px-8 py-4 font-medium transition-colors hover:bg-gray-100">
			Get in Touch
		</a>
	</div>
</div>

<!-- Where to Find Us - Map Section -->
<div class="bg-gray-50 py-16 md:py-24">
	<div class="container mx-auto px-4">
		<div class="mb-12 text-center">
			<h2 class="text-3xl font-bold text-gray-800 md:text-4xl">Where to Find Us</h2>
			<p class="mt-2 text-gray-600">Visit our location at Jamhuri Park Showground, Nairobi.</p>
		</div>

		<div class="mb-12 grid grid-cols-1 gap-12 lg:grid-cols-2">
			<div class="rounded-lg bg-white p-8 shadow-lg">
				<h3 class="mb-6 text-2xl font-bold text-gray-800">Contact Information</h3>

				<div class="space-y-4">
					<div class="flex items-start">
						<div class="text-primary mt-1 mr-4">
							<i class="bi bi-geo-alt-fill text-xl"></i>
						</div>
						<div>
							<h4 class="font-bold">Address:</h4>
							<p class="text-gray-600">{contactInfo.address.line1}</p>
							<p class="text-gray-600">{contactInfo.address.line2}</p>
						</div>
					</div>

					<div class="flex items-start">
						<div class="text-primary mt-1 mr-4">
							<i class="bi bi-telephone-fill text-xl"></i>
						</div>
						<div>
							<h4 class="font-bold">Phone:</h4>
							<p class="text-gray-600">{contactInfo.phone}</p>
						</div>
					</div>

					<div class="flex items-start">
						<div class="text-primary mt-1 mr-4">
							<i class="bi bi-envelope-fill text-xl"></i>
						</div>
						<div>
							<h4 class="font-bold">Email:</h4>
							<p class="text-gray-600">{contactInfo.email}</p>
						</div>
					</div>

					<div class="flex items-start">
						<div class="text-primary mt-1 mr-4">
							<i class="bi bi-mailbox text-xl"></i>
						</div>
						<div>
							<h4 class="font-bold">Postal Address:</h4>
							<p class="text-gray-600">{contactInfo.postal}</p>
						</div>
					</div>
				</div>
			</div>

			<div class="relative h-96 w-full overflow-hidden rounded-lg shadow-xl md:h-full">
				<iframe
					src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3988.851757999198!2d36.80280867496561!3d-1.265014498728368!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x182f1741713610c1%3A0x50a21b4b1a3979a8!2sLa%20Foret%20Conference%20Centre!5e0!3m2!1sen!2ske!4v1714901000000!5m2!1sen!2ske"
					width="100%"
					height="100%"
					style="border:0;"
					allowfullscreen
					loading="lazy"
					referrerpolicy="no-referrer-when-downgrade"
					title="Jamhuri Park Showground Location"
				></iframe>
			</div>
		</div>

		<div class="text-center">
			<a href="/contact" class="bg-primary hover:bg-primary/90 inline-block rounded px-8 py-4 font-medium text-white transition-all">
				Contact Us for More Information
			</a>
		</div>
	</div>
</div>
