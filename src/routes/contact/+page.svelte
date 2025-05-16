<script lang="ts">
	// Contact Page Content
	const contactInfo = {
		address: {
			line1: 'Steward House, Jamhuri Park Showground',
			line2: 'Off Ngong Road, Nairobi'
		},
		phone: '+254 786 926 142',
		email: 'info@bsl.co.ke',
		postal: 'P.O. Box 13338 – 00200, Nairobi'
	};

	const formFields = {
		name: {
			label: 'Full Name',
			placeholder: 'Enter your full name',
			required: true
		},
		email: {
			label: 'Email Address',
			placeholder: 'Enter your email address',
			required: true
		},
		phone: {
			label: 'Phone Number',
			placeholder: 'Enter your phone number',
			required: false
		},
		company: {
			label: 'Company Name',
			placeholder: 'Enter your company name',
			required: false
		},
		subject: {
			label: 'Subject',
			placeholder: 'What is this regarding?',
			required: true
		},
		message: {
			label: 'Message',
			placeholder: 'How can we help you?',
			required: true
		}
	};

	// Form state
	let name = '';
	let email = '';
	let phone = '';
	let company = '';
	let subject = '';
	let message = '';
	let formSubmitted = false;
	let formSubmitting = false;

	// Handle form submission
	const handleSubmit = () => {
		formSubmitting = true;

		// Simulate form submission with timeout
		setTimeout(() => {
			formSubmitting = false;
			formSubmitted = true;

			// Reset form fields
			name = '';
			email = '';
			phone = '';
			company = '';
			subject = '';
			message = '';
		}, 1000);
	};
</script>

<!-- Hero Section -->
<div class="relative bg-gradient-to-r from-blue-800 to-indigo-900 py-24 md:py-32">
	<div class="absolute inset-0 opacity-20">
		<div class="h-full w-full bg-[url('/heroBg.jpg')] bg-cover bg-center"></div>
	</div>
	<div class="relative container mx-auto px-4 text-center">
		<h1 class="mb-4 text-4xl font-bold tracking-tight text-white md:text-5xl lg:text-6xl">Contact Us</h1>
		<p class="mx-auto mt-6 max-w-2xl text-xl font-light text-white/90">
			Get in touch with our team to discuss how we can help your business succeed with our software solutions.
		</p>
	</div>
</div>

<!-- Contact Information Section -->
<div class="container mx-auto px-4 py-16">
	<div class="grid grid-cols-1 gap-12 lg:grid-cols-3">
		<!-- Contact Details -->
		<div class="lg:col-span-1">
			<h2 class="mb-8 text-3xl font-bold text-gray-800">Get in Touch</h2>

			<div class="space-y-8">
				<!-- Address -->
				<div class="flex items-start">
					<div class="bg-primary/10 text-primary flex h-12 w-12 items-center justify-center rounded-lg">
						<i class="bi bi-geo-alt-fill text-xl"></i>
					</div>
					<div class="ml-4">
						<h3 class="mb-1 text-xl font-bold">Visit Us</h3>
						<p class="text-gray-600">{contactInfo.address.line1}</p>
						<p class="text-gray-600">{contactInfo.address.line2}</p>
					</div>
				</div>

				<!-- Phone -->
				<div class="flex items-start">
					<div class="bg-primary/10 text-primary flex h-12 w-12 items-center justify-center rounded-lg">
						<i class="bi bi-telephone-fill text-xl"></i>
					</div>
					<div class="ml-4">
						<h3 class="mb-1 text-xl font-bold">Call Us</h3>
						<p class="text-gray-600">{contactInfo.phone}</p>
					</div>
				</div>

				<!-- Email -->
				<div class="flex items-start">
					<div class="bg-primary/10 text-primary flex h-12 w-12 items-center justify-center rounded-lg">
						<i class="bi bi-envelope-fill text-xl"></i>
					</div>
					<div class="ml-4">
						<h3 class="mb-1 text-xl font-bold">Email Us</h3>
						<p class="text-gray-600">{contactInfo.email}</p>
					</div>
				</div>

				<!-- Postal -->
				<div class="flex items-start">
					<div class="bg-primary/10 text-primary flex h-12 w-12 items-center justify-center rounded-lg">
						<i class="bi bi-mailbox text-xl"></i>
					</div>
					<div class="ml-4">
						<h3 class="mb-1 text-xl font-bold">Postal Address</h3>
						<p class="text-gray-600">{contactInfo.postal}</p>
					</div>
				</div>

				<!-- Business Hours -->
				<div class="flex items-start">
					<div class="bg-primary/10 text-primary flex h-12 w-12 items-center justify-center rounded-lg">
						<i class="bi bi-clock-fill text-xl"></i>
					</div>
					<div class="ml-4">
						<h3 class="mb-1 text-xl font-bold">Business Hours</h3>
						<p class="text-gray-600">Monday - Friday: 8:00 AM - 5:00 PM</p>
						<p class="text-gray-600">Saturday & Sunday: Closed</p>
					</div>
				</div>
			</div>

			<!-- Social Media Links -->
			<div class="mt-12">
				<h3 class="mb-4 text-xl font-bold">Connect With Us</h3>
				<div class="flex space-x-4">
					<a
						href="/#"
						aria-label="facebook"
						class="bg-primary/10 text-primary hover:bg-primary flex h-10 w-10 items-center justify-center rounded-full transition-colors hover:text-white"
					>
						<i class="bi bi-facebook"></i>
					</a>
					<a
						href="/#"
						aria-label="x"
						class="bg-primary/10 text-primary hover:bg-primary flex h-10 w-10 items-center justify-center rounded-full transition-colors hover:text-white"
					>
						<i class="bi bi-twitter-x"></i>
					</a>
					<a
						href="/#"
						aria-label="linkedin"
						class="bg-primary/10 text-primary hover:bg-primary flex h-10 w-10 items-center justify-center rounded-full transition-colors hover:text-white"
					>
						<i class="bi bi-linkedin"></i>
					</a>
					<a
						href="/#"
						aria-label="instagram"
						class="bg-primary/10 text-primary hover:bg-primary flex h-10 w-10 items-center justify-center rounded-full transition-colors hover:text-white"
					>
						<i class="bi bi-instagram"></i>
					</a>
				</div>
			</div>
		</div>

		<!-- Contact Form -->
		<div class="rounded-lg bg-white p-8 shadow-lg lg:col-span-2">
			<h2 class="mb-8 text-3xl font-bold text-gray-800">Send Us a Message</h2>

			{#if formSubmitted}
				<div class="rounded-lg bg-green-50 p-4 text-green-800">
					<div class="flex">
						<div class="flex-shrink-0">
							<i class="bi bi-check-circle-fill text-xl text-green-600"></i>
						</div>
						<div class="ml-3">
							<h3 class="text-lg font-medium">Message sent successfully!</h3>
							<p class="mt-2">Thank you for contacting us. Our team will get back to you as soon as possible.</p>
							<button onclick={() => (formSubmitted = false)} class="mt-3 rounded-md bg-green-600 px-4 py-2 text-white hover:bg-green-700">
								Send another message
							</button>
						</div>
					</div>
				</div>
			{:else}
				<form onsubmit={handleSubmit} class="space-y-6">
					<div class="grid grid-cols-1 gap-6 md:grid-cols-2">
						<!-- Name Field -->
						<div>
							<label for="name" class="mb-1 block text-sm font-medium text-gray-700">
								{formFields.name.label}
								{#if formFields.name.required}<span class="text-red-500">*</span>{/if}
							</label>
							<input
								type="text"
								id="name"
								bind:value={name}
								placeholder={formFields.name.placeholder}
								class="focus:border-primary focus:ring-primary w-full rounded-md border-gray-300 shadow-sm"
								required={formFields.name.required}
							/>
						</div>

						<!-- Email Field -->
						<div>
							<label for="email" class="mb-1 block text-sm font-medium text-gray-700">
								{formFields.email.label}
								{#if formFields.email.required}<span class="text-red-500">*</span>{/if}
							</label>
							<input
								type="email"
								id="email"
								bind:value={email}
								placeholder={formFields.email.placeholder}
								class="focus:border-primary focus:ring-primary w-full rounded-md border-gray-300 shadow-sm"
								required={formFields.email.required}
							/>
						</div>

						<!-- Phone Field -->
						<div>
							<label for="phone" class="mb-1 block text-sm font-medium text-gray-700">
								{formFields.phone.label}
								{#if formFields.phone.required}<span class="text-red-500">*</span>{/if}
							</label>
							<input
								type="tel"
								id="phone"
								bind:value={phone}
								placeholder={formFields.phone.placeholder}
								class="focus:border-primary focus:ring-primary w-full rounded-md border-gray-300 shadow-sm"
								required={formFields.phone.required}
							/>
						</div>

						<!-- Company Field -->
						<div>
							<label for="company" class="mb-1 block text-sm font-medium text-gray-700">
								{formFields.company.label}
								{#if formFields.company.required}<span class="text-red-500">*</span>{/if}
							</label>
							<input
								type="text"
								id="company"
								bind:value={company}
								placeholder={formFields.company.placeholder}
								class="focus:border-primary focus:ring-primary w-full rounded-md border-gray-300 shadow-sm"
								required={formFields.company.required}
							/>
						</div>
					</div>

					<!-- Subject Field -->
					<div>
						<label for="subject" class="mb-1 block text-sm font-medium text-gray-700">
							{formFields.subject.label}
							{#if formFields.subject.required}<span class="text-red-500">*</span>{/if}
						</label>
						<input
							type="text"
							id="subject"
							bind:value={subject}
							placeholder={formFields.subject.placeholder}
							class="focus:border-primary focus:ring-primary w-full rounded-md border-gray-300 shadow-sm"
							required={formFields.subject.required}
						/>
					</div>

					<!-- Message Field -->
					<div>
						<label for="message" class="mb-1 block text-sm font-medium text-gray-700">
							{formFields.message.label}
							{#if formFields.message.required}<span class="text-red-500">*</span>{/if}
						</label>
						<textarea
							id="message"
							bind:value={message}
							placeholder={formFields.message.placeholder}
							rows="5"
							class="focus:border-primary focus:ring-primary w-full rounded-md border-gray-300 shadow-sm"
							required={formFields.message.required}
						></textarea>
					</div>

					<!-- Submit Button -->
					<div class="flex items-center justify-between">
						<p class="text-sm text-gray-500">Fields marked with <span class="text-red-500">*</span> are required</p>
						<button
							type="submit"
							class="bg-primary hover:bg-primary/90 inline-flex w-auto items-center justify-center rounded-md px-8 py-3 font-medium text-white transition-colors disabled:opacity-70"
							disabled={formSubmitting}
						>
							{#if formSubmitting}
								<span class="mr-2 h-4 w-4 animate-spin rounded-full border-2 border-white border-t-transparent"></span>
								Sending...
							{:else}
								Send Message
							{/if}
						</button>
					</div>
				</form>
			{/if}
		</div>
	</div>
</div>

<!-- Map Section -->
<div class="py-16">
	<div class="container mx-auto px-4">
		<h2 class="mb-8 text-center text-3xl font-bold text-gray-800">Our Location</h2>
		<div class="relative h-[500px] w-full overflow-hidden rounded-lg shadow-xl">
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
</div>

<!-- FAQ Section -->
<div class="bg-gray-50 py-16">
	<div class="container mx-auto px-4">
		<h2 class="mb-12 text-center text-3xl font-bold text-gray-800">Frequently Asked Questions</h2>

		<!-- <div class="mx-auto grid max-w-4xl grid-cols-1 gap-6">
			<!-- FAQ Item 1 --
			<div class="rounded-lg bg-white p-6 shadow-md">
				<h3 class="text-xl font-bold text-gray-800">What services does Brisk Solutions offer?</h3>
				<p class="mt-2 text-gray-600">
					We offer a range of software solutions including enterprise resource planning (ERP) systems, human resource management systems,
					business process automation, SAAS solutions, and more. Our focus is on creating custom solutions that meet your specific business
					needs.
				</p>
			</div>

			<!-- FAQ Item 2 --
			<div class="rounded-lg bg-white p-6 shadow-md">
				<h3 class="text-xl font-bold text-gray-800">How long does it take to implement your solutions?</h3>
				<p class="mt-2 text-gray-600">
					Implementation timelines vary based on the complexity of the project and your specific requirements. We work closely with you to
					establish realistic timelines and ensure a smooth implementation process. Contact us for a more specific estimate for your
					project.
				</p>
			</div>

			<!-- FAQ Item 3 --
			<div class="rounded-lg bg-white p-6 shadow-md">
				<h3 class="text-xl font-bold text-gray-800">Do you offer ongoing support after implementation?</h3>
				<p class="mt-2 text-gray-600">
					Yes, we provide comprehensive support and maintenance services to ensure your systems continue to run efficiently. Our team is
					available to address any issues, provide updates, and help you maximize the value of your software investment.
				</p>
			</div>

			<!-- FAQ Item 4 --
			<div class="rounded-lg bg-white p-6 shadow-md">
				<h3 class="text-xl font-bold text-gray-800">Can you customize your solutions for our specific industry?</h3>
				<p class="mt-2 text-gray-600">
					Absolutely! We specialize in creating customized solutions tailored to your industry's unique requirements and challenges. We take
					the time to understand your business processes and develop software that aligns with your specific needs.
				</p>
			</div>
		</div> -->
	</div>
</div>

<!-- CTA Section -->
<div class="bg-primary py-16 text-center">
	<div class="container mx-auto px-4">
		<h2 class="mb-6 text-3xl font-bold text-white md:text-4xl">Ready to transform your business?</h2>
		<p class="mx-auto mb-10 max-w-2xl text-lg text-white/90">
			Partner with Brisk Solutions for innovative software solutions that drive efficiency and growth.
		</p>
		<div class="flex flex-wrap justify-center gap-4">
			<a
				href="/about"
				class="inline-block rounded-md border-2 border-white px-8 py-3 font-medium text-white transition-all hover:bg-white/10"
			>
				Learn More About Us
			</a>
			<a href="/services" class="text-primary inline-block rounded-md bg-white px-8 py-3 font-medium transition-all hover:bg-white/90">
				Explore Our Services
			</a>
		</div>
	</div>
</div>
