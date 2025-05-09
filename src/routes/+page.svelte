<script>
	const projects = [
		{
			title: 'BuzzChat (WIP)',
			description:
				'End-to-end encrypted chat app with Go backend, Svelte frontend, and Valkey cache. Because who needs plain old chat when you can have secure, fast, and encrypted messages?',
			link: 'https://buzz-chat-alpha.vercel.app',
			icon: '💬',
			tags: ['Go', 'Svelte', 'PostgreSQL', 'Valkey', 'TailwindCSS']
		},
		{
			title: 'BugBee',
			description:
				'A social platform with communities, chat, video calls, and NSFW detection. Your new favorite place to talk, share, and avoid unwanted surprises.',
			link: 'https://thebugbee.vercel.app',
			icon: '🐝',
			tags: ['React', 'Go', 'NodeJS', 'FastAPI', 'PostgreSQL', 'Valkey']
		},
		{
			title: 'Immerse',
			description: 'Where the only thing buffering is your self-control.',
			link: 'https://github.com/RickinShah/Immerse',
			icon: '📺',
			tags: ['FFmpeg', 'Java', 'Spring', 'Nginx', 'HLS', 'MariaDB', 'Shell Script']
		},
		{
			title: 'Image Editor',
			description: 'Open it up, edit a photo, and pretend it’s Photoshop for a second.',
			link: 'https://github.com/RickinShah/Image-Editor',
			icon: '🖼️',
			tags: ['Python', 'Tkinter', 'PIL']
		}
	];

	const miscellaneous = [
		{
			title: 'Hyprland Configs',
			description: 'Custom setup, because default is for amateurs.',
			icon: '💻',
			link: 'https://github.com/RickinShah/hyprland-dotfiles'
		},
		{
			title: 'Neovim Configs',
			description: 'Who needs a mouse when you’ve got muscle memory and regret?',
			icon: '🎨',
			link: 'https://github.com/RickinShah/nvim-config'
		}
	];

	const techStack = [
		{ name: 'Go', logo: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/go/go-original.svg' },
		{
			name: 'Java',
			logo: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/java/java-original.svg'
		},
		{
			name: 'C/C++',
			logo: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/cplusplus/cplusplus-original.svg'
		},
		{
			name: 'Python',
			logo: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg'
		},
		{
			name: 'Spring Boot',
			logo: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/spring/spring-original.svg'
		},
		{ name: 'FastAPI', logo: 'https://logo.svgcdn.com/d/fastapi-plain-8x.png' },
		{
			name: 'Svelte',
			logo: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/svelte/svelte-original.svg'
		},
		{
			name: 'React',
			logo: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/react/react-original.svg'
		},
		{
			name: 'FFmpeg',
			logo: 'https://upload.wikimedia.org/wikipedia/commons/thumb/7/76/FFmpeg_icon.svg/2048px-FFmpeg_icon.svg.png'
		},
		{
			name: 'PostgreSQL',
			logo: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/postgresql/postgresql-original.svg'
		},
		{
			name: 'Valkey / Redis',
			logo: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/redis/redis-original.svg'
		},
		{
			name: 'Docker',
			logo: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/docker/docker-original.svg'
		}
		// {
		// 	name: 'Nginx',
		// 	logo: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nginx/nginx-original.svg'
		// },
		// { name: 'Neovim', logo: 'https://upload.wikimedia.org/wikipedia/commons/3/3a/Neovim-mark.svg' },
		// {
		// 	name: 'VSCode',
		// 	logo: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/vscode/vscode-original.svg'
		// },
		// {
		// 	name: 'JetBrains IDEA',
		// 	logo: 'https://resources.jetbrains.com/storage/products/intellij-idea/img/meta/intellij-idea_logo_300x300.png'
		// },
		// { name: 'Eclipse', logo: 'https://logodix.com/logo/732150.png' },
		// {
		// 	name: 'Arch Linux',
		// 	logo: 'https://cdn0.iconfinder.com/data/icons/flat-round-system/512/archlinux-1024.png'
		// }
	];

	let currentIndex = 0;
	let interval;
	let scrollY = 0;
	let showMiniProfile = false;

	function startTechRotation() {
		interval = setInterval(() => {
			currentIndex = (currentIndex + 1) % techStack.length;
		}, 2000);
	}

	function stopTechRotation() {
		clearInterval(interval);
	}

	function handleScroll() {
		scrollY = window.scrollY;
		showMiniProfile = scrollY > window.innerHeight * 0.8;
	}
</script>

<svelte:head>
	<link
		href="https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;600;700&family=Space+Grotesk:wght@300;400;500;600;700&display=swap"
		rel="stylesheet"
	/>
	<meta name="viewport" content="width=device-width, initial-scale=1.0" />
</svelte:head>

<svelte:window on:scroll={handleScroll} />

<main
	class="overflow-hidden bg-gradient-to-br from-violet-950 via-slate-900 to-black font-sans text-white"
>
	<div class="absolute inset-0 overflow-hidden">
		<div class="bg-grid-pattern absolute inset-0 opacity-5"></div>
		<div class="absolute top-0 left-0 h-full w-full">
			<div
				class="blur-5xl animate-blob absolute top-10 left-10 h-64 w-64 rounded-full bg-purple-600 opacity-10 mix-blend-multiply filter md:h-96 md:w-96"
			></div>
			<div
				class="blur-5xl animate-blob animation-delay-2000 absolute top-5 right-10 h-56 w-56 rounded-full bg-teal-600 opacity-10 mix-blend-multiply filter md:h-80 md:w-80"
			></div>
			<div
				class="blur-5xl animate-blob animation-delay-4000 absolute bottom-10 left-20 h-48 w-48 rounded-full bg-indigo-600 opacity-10 mix-blend-multiply filter md:h-72 md:w-72"
			></div>
		</div>
	</div>

	<div class="relative z-10 mx-auto max-w-7xl px-4 py-6 sm:px-6 lg:px-8">
		<!-- Header section -->
		<header
			class="fixed top-0 right-0 left-0 z-50 flex h-16 items-center bg-slate-900/80 shadow-md backdrop-blur-md transition-all duration-500"
		>
			<div class="mx-auto flex w-full max-w-7xl items-center justify-between px-4 sm:px-6 lg:px-8">
				<a
					href="#"
					class="flex items-center gap-2 text-lg font-bold tracking-tight text-teal-400 transition-all duration-500 sm:gap-3 sm:text-xl"
				>
					<div
						class="relative hidden h-8 w-8 flex-shrink-0 transform overflow-hidden transition-all duration-500 ease-in-out sm:h-10 sm:w-10 md:inline"
						style="width: {showMiniProfile ? '40px' : '0px'}; opacity: {showMiniProfile
							? '1'
							: '0'};"
					>
						<img
							src="/profile_pic.jpg"
							alt="Rickin"
							class="h-full w-full rounded-full border border-teal-400 object-cover"
						/>
					</div>
					<span
						class="hidden transform overflow-hidden bg-gradient-to-r from-teal-400 to-purple-500 bg-clip-text text-sm text-transparent transition-all duration-500 md:inline md:text-lg"
						style="max-width: {showMiniProfile ? '150px' : '0px'}; opacity: {showMiniProfile
							? '1'
							: '0'};"
					>
						Rickin Shah
					</span>
				</a>
				<div class="flex flex-1 justify-center sm:justify-end">
					<nav>
						<ul class="flex space-x-0 sm:space-x-6 md:space-x-4 lg:space-x-8">
							<li><a href="#about" class="transition-colors hover:text-teal-400">About</a></li>
							<li>
								<a href="#projects" class="transition-colors hover:text-teal-400">Projects</a>
							</li>
							<li>
								<a href="#miscellaneous" class="transition-colors hover:text-teal-400"
									>Miscellaneous</a
								>
							</li>
							<li>
								<a href="#tech" class="transition-colors hover:text-teal-400">Digital Arsenal</a>
							</li>
						</ul>
					</nav>
				</div>
			</div>
		</header>

		<!-- Hero Section -->
		<section id="about" class="relative flex min-h-screen flex-col justify-center pt-16 md:pt-20">
			<div class="flex min-h-[calc(100vh-4rem)] flex-col items-center gap-8 md:flex-row md:gap-12">
				<div class="animate-fade-in order-2 space-y-4 md:order-1 md:w-1/2">
					<div class="inline-block">
						<span class="text-base font-semibold text-teal-400 sm:text-lg">Hello, I'm</span>
					</div>
					<h1 class="text-4xl font-bold tracking-tight sm:text-5xl md:text-6xl lg:text-7xl">
						<span class="bg-gradient-to-r from-teal-400 to-purple-500 bg-clip-text text-transparent"
							>Rickin Shah</span
						>
					</h1>
					<p class="max-w-md text-base text-gray-300 sm:max-w-lg sm:text-lg">
						Building software, one line of code and one cup of coffee at a time.
					</p>
					<div class="flex flex-wrap gap-3 pt-3 sm:gap-4 sm:pt-4">
						<a
							href="https://github.com/RickinShah"
							class="group flex items-center gap-2 rounded-full bg-gradient-to-r from-teal-500 to-teal-700 px-4 py-2 text-sm transition-all hover:shadow-lg hover:shadow-teal-500/20 sm:px-5 sm:py-3 sm:text-base"
						>
							<svg class="h-4 w-4 sm:h-5 sm:w-5" fill="currentColor" viewBox="0 0 24 24">
								<path
									fill-rule="evenodd"
									d="M12 2C6.477 2 2 6.484 2 12.017c0 4.425 2.865 8.18 6.839 9.504.5.092.682-.217.682-.483 0-.237-.008-.868-.013-1.703-2.782.605-3.369-1.343-3.369-1.343-.454-1.158-1.11-1.466-1.11-1.466-.908-.62.069-.608.069-.608 1.003.07 1.531 1.032 1.531 1.032.892 1.53 2.341 1.088 2.91.832.092-.647.35-1.088.636-1.338-2.22-.253-4.555-1.113-4.555-4.951 0-1.093.39-1.988 1.029-2.688-.103-.253-.446-1.272.098-2.65 0 0 .84-.27 2.75 1.026A9.564 9.564 0 0112 6.844c.85.004 1.705.115 2.504.337 1.909-1.296 2.747-1.027 2.747-1.027.546 1.379.202 2.398.1 2.651.64.7 1.028 1.595 1.028 2.688 0 3.848-2.339 4.695-4.566 4.943.359.309.678.92.678 1.855 0 1.338-.012 2.419-.012 2.747 0 .268.18.58.688.482A10.019 10.019 0 0022 12.017C22 6.484 17.522 2 12 2z"
									clip-rule="evenodd"
								></path>
							</svg>
							<span class="hidden md:inline">GitHub</span>
						</a>
						<a
							href="https://www.linkedin.com/in/rickin-shah"
							class="group flex items-center gap-2 rounded-full bg-gradient-to-r from-blue-500 to-blue-700 px-4 py-2 text-sm transition-all hover:shadow-lg hover:shadow-blue-500/20 sm:px-5 sm:py-3 sm:text-base"
						>
							<svg class="h-4 w-4 sm:h-5 sm:w-5" fill="currentColor" viewBox="0 0 24 24">
								<path
									d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z"
								></path>
							</svg>
							<span class="hidden md:inline">LinkedIn</span>
						</a>
					</div>
				</div>
				<div class="animate-float order-1 flex justify-center pb-8 md:order-2 md:w-1/2 md:pb-0">
					<div class="relative">
						<div
							class="absolute inset-0 animate-pulse rounded-full bg-gradient-to-r from-teal-500 to-purple-600 opacity-30 blur-xl"
						></div>
						<img
							src="/profile_pic.jpg"
							alt="Rickin"
							class="relative h-48 w-48 rounded-full border-4 border-teal-400 object-cover object-center shadow-2xl sm:h-56 sm:w-56 md:h-64 md:w-64"
						/>
					</div>
				</div>
			</div>

			<div
				class="absolute bottom-24 left-1/2 -translate-x-1/2 transform animate-bounce md:bottom-16"
			>
				<svg
					class="h-5 w-5 text-gray-400 sm:h-6 sm:w-6"
					fill="none"
					stroke="currentColor"
					viewBox="0 0 24 24"
				>
					<path
						stroke-linecap="round"
						stroke-linejoin="round"
						stroke-width="2"
						d="M19 14l-7 7m0 0l-7-7m7 7V3"
					></path>
				</svg>
			</div>
		</section>
		<!-- Projects Section -->
		<section id="projects" class="scroll-m-16 pb-16">
			<div class="mx-auto max-w-4xl">
				<h2 class="mb-2 text-center text-3xl font-bold sm:text-4xl">
					<span class="bg-gradient-to-r from-teal-400 to-purple-500 bg-clip-text text-transparent"
						>Projects</span
					>
				</h2>
				<p class="mb-12 text-center text-gray-400 sm:mb-16">Where code meets caffeine</p>
				<div class="space-y-10">
					{#each projects as project, i (i)}
						<div class="group">
							<a href={project.link} class="block transform transition-all hover:-translate-y-1">
								<div
									class="relative overflow-hidden rounded-2xl bg-gradient-to-b from-slate-800 to-slate-900"
								>
									<div
										class="animate-gradient absolute inset-0 bg-gradient-to-r from-teal-500 to-purple-500 opacity-50 transition-opacity group-hover:opacity-70"
									></div>
									<div
										class="absolute inset-0.5 overflow-hidden rounded-2xl bg-gradient-to-b from-slate-800 to-slate-900"
									></div>
									<div class="relative p-6 sm:p-8">
										<div
											class="flex flex-col items-start sm:flex-row sm:items-start sm:justify-between"
										>
											<div>
												<span class="mb-3 block text-3xl sm:mb-4 sm:text-4xl">{project.icon}</span>
												<h3
													class="mb-2 bg-gradient-to-r from-teal-400 to-purple-400 bg-clip-text text-xl font-bold text-transparent sm:mb-3 sm:text-2xl"
												>
													{project.title}
												</h3>
												<p class="text-sm text-gray-300 sm:text-base">{project.description}</p>
											</div>
											<div
												class="mt-4 hidden text-teal-400 opacity-0 transition-opacity group-hover:opacity-100 sm:mt-0 sm:block"
											>
												<svg
													class="h-5 w-5 sm:h-6 sm:w-6"
													fill="none"
													stroke="currentColor"
													viewBox="0 0 24 24"
												>
													<path
														stroke-linecap="round"
														stroke-linejoin="round"
														stroke-width="2"
														d="M14 5l7 7m0 0l-7 7m7-7H3"
													></path>
												</svg>
											</div>
										</div>
										<div class="mt-4 flex flex-wrap gap-2">
											{#each project.tags as tag, i (i)}
												<span
													class="rounded-full bg-slate-700/50 px-2.5 py-1 text-xs text-teal-300 sm:px-3 sm:text-sm"
													>{tag}</span
												>
											{/each}
										</div>
										<div class="mt-4 border-t border-gray-700/50 pt-4 sm:mt-6 sm:pt-6">
											<div class="flex items-center text-sm text-gray-400 sm:text-base">
												<span>View Project</span>
											</div>
										</div>
									</div>
								</div>
							</a>
						</div>
					{/each}
				</div>
			</div>
		</section>

		<section id="miscellaneous" class="scroll-m-16 py-16">
			<div class="mx-auto max-w-4xl">
				<h2 class="mb-2 text-center text-3xl font-bold sm:text-4xl">
					<span class="bg-gradient-to-r from-teal-400 to-purple-500 bg-clip-text text-transparent"
						>Miscellaneous</span
					>
				</h2>
				<p class="mb-12 text-center text-gray-400 sm:mb-16">
					Because default settings are for the weak
				</p>
				<div class="space-y-10">
					{#each miscellaneous as misc, i (i)}
						<div class="group">
							<a href={misc.link} class="block transform transition-all hover:-translate-y-1">
								<div
									class="relative overflow-hidden rounded-2xl bg-gradient-to-b from-slate-800 to-slate-900"
								>
									<div
										class="animate-gradient absolute inset-0 bg-gradient-to-r from-teal-500 to-purple-500 opacity-50 transition-opacity group-hover:opacity-70"
									></div>
									<div
										class="absolute inset-0.5 overflow-hidden rounded-2xl bg-gradient-to-b from-slate-800 to-slate-900"
									></div>
									<div class="relative p-6 sm:p-8">
										<div
											class="flex flex-col items-start sm:flex-row sm:items-start sm:justify-between"
										>
											<div>
												<span class="mb-3 block text-3xl sm:mb-4 sm:text-4xl">{misc.icon}</span>
												<h3
													class="mb-2 bg-gradient-to-r from-teal-400 to-purple-400 bg-clip-text text-xl font-bold text-transparent sm:mb-3 sm:text-2xl"
												>
													{misc.title}
												</h3>
												<p class="text-sm text-gray-300 sm:text-base">{misc.description}</p>
											</div>
											<div
												class="mt-4 hidden text-teal-400 opacity-0 transition-opacity group-hover:opacity-100 sm:mt-0 sm:block"
											>
												<svg
													class="h-5 w-5 sm:h-6 sm:w-6"
													fill="none"
													stroke="currentColor"
													viewBox="0 0 24 24"
												>
													<path
														stroke-linecap="round"
														stroke-linejoin="round"
														stroke-width="2"
														d="M14 5l7 7m0 0l-7 7m7-7H3"
													></path>
												</svg>
											</div>
										</div>
										<!-- <div class="mt-4 flex flex-wrap gap-2">
											{#each project.tags as tag, i (i)}
												<span
													class="rounded-full bg-slate-700/50 px-2.5 py-1 text-xs text-teal-300 sm:px-3 sm:text-sm"
													>{tag}</span
												>
											{/each}
										</div> -->
										<div class="mt-4 border-t border-gray-700/50 pt-4 sm:mt-6 sm:pt-6">
											<div class="flex items-center text-sm text-gray-400 sm:text-base">
												<span>View Repo</span>
											</div>
										</div>
									</div>
								</div>
							</a>
						</div>
					{/each}
				</div>
			</div>
		</section>

		<!-- Tech Stack Section -->
		<section id="tech" class="scroll-m-16 py-16">
			<h2 class="mb-2 text-center text-3xl font-bold sm:text-4xl">
				<span class="bg-gradient-to-r from-teal-400 to-purple-500 bg-clip-text text-transparent"
					>Digital Arsenal</span
				>
			</h2>
			<p class="mb-12 text-center text-gray-400 sm:mb-16">What I bring to the coding battlefield</p>
			<div
				class="grid grid-cols-2 gap-6 sm:grid-cols-3 md:grid-cols-4 lg:grid-cols-5 xl:grid-cols-6"
			>
				{#each techStack as tech, i (i)}
					<div class="group flex flex-col items-center justify-center">
						<div
							class="relative mb-3 h-12 w-12 transform transition-all duration-300 group-hover:scale-110 sm:h-14 sm:w-14 md:h-16 md:w-16"
						>
							<div
								class="absolute inset-0 rounded-full bg-gradient-to-r from-teal-500 to-purple-500 opacity-0 blur-md transition-opacity group-hover:opacity-20"
							></div>
							<div
								class="relative flex h-full w-full items-center justify-center rounded-full border border-slate-700 bg-slate-800/80 p-2 transition-colors group-hover:border-teal-500 sm:p-3"
							>
								<img
									src={tech.logo}
									alt={tech.name}
									class="h-full w-full object-contain brightness-90 filter transition-all group-hover:brightness-110"
								/>
							</div>
						</div>
						<span
							class="text-xs text-gray-400 transition-colors group-hover:text-teal-400 sm:text-sm"
							>{tech.name}</span
						>
					</div>
				{/each}
			</div>
		</section>

		<!-- Contact CTA -->
		<section class="py-16">
			<div class="relative mx-auto max-w-4xl overflow-hidden rounded-3xl p-8 text-center sm:p-12">
				<div
					class="absolute inset-0 bg-gradient-to-r from-teal-900/80 via-slate-900/90 to-purple-900/80"
				></div>
				<div class="bg-grid-pattern absolute inset-0 opacity-10"></div>
				<div class="absolute inset-0 overflow-hidden">
					{#each Array(10) as _, i (i)}
						<div
							class="animate-floating absolute h-1.5 w-1.5 rounded-full bg-teal-400/30 sm:h-2 sm:w-2"
							style="top: {Math.random() * 100}%; left: {Math.random() *
								100}%; animation-delay: {i * 0.4}s;"
						></div>
					{/each}
				</div>
				<div class="relative z-10">
					<h2 class="mb-4 text-2xl font-bold sm:text-3xl">Interested in working together?</h2>
					<p class="mb-6 text-gray-300 sm:mb-8">Let's build something amazing!</p>
					<a
						href="mailto:rickin.shah17403@gmail.com"
						class="inline-block transform rounded-full bg-gradient-to-r from-teal-500 to-purple-600 px-6 py-3 text-sm font-medium transition-all hover:-translate-y-1 hover:shadow-lg hover:shadow-teal-500/20 sm:px-8 sm:py-4 sm:text-base"
					>
						Get In Touch
					</a>
				</div>
			</div>
		</section>

		<!-- Footer -->
		<footer class="border-t border-slate-800/50 py-8 text-center text-gray-500">
			<p class="text-sm sm:text-base">
				© 2025 Rickin Shah — Built with Svelte & TailwindCSS (and probably a lot of caffeine)
			</p>

			<div class="mt-4 flex justify-center space-x-4 sm:space-x-6">
				<a
					href="https://instagram.com/rickin_shah"
					class="text-gray-400 transition-colors hover:text-teal-400"
				>
					<span class="sr-only">Instagram</span>
					<svg class="h-5 w-5" fill="currentColor" viewBox="0 0 24 24">
						<path
							d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zM12 0C8.741 0 8.333.014 7.053.072 2.695.272.273 2.69.073 7.052.014 8.333 0 8.741 0 12c0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98C8.333 23.986 8.741 24 12 24c3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98C15.668.014 15.259 0 12 0zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162 0 3.403 2.759 6.162 6.162 6.162 3.403 0 6.162-2.759 6.162-6.162 0-3.403-2.759-6.162-6.162-6.162zM12 16a4 4 0 110-8 4 4 0 010 8zm6.406-11.845a1.44 1.44 0 100 2.881 1.44 1.44 0 000-2.881z"
						></path>
					</svg>
				</a>

				<a href="#" class="text-gray-400 transition-colors hover:text-teal-400">
					<span class="sr-only">Twitter</span>
					<svg class="h-5 w-5" fill="currentColor" viewBox="0 0 24 24">
						<path
							d="M8.29 20.251c7.547 0 11.675-6.253 11.675-11.675 0-.178 0-.355-.012-.53A8.348 8.348 0 0022 5.92a8.19 8.19 0 01-2.357.646 4.118 4.118 0 001.804-2.27 8.224 8.224 0 01-2.605.996 4.107 4.107 0 00-6.993 3.743 11.65 11.65 0 01-8.457-4.287 4.106 4.106 0 001.27 5.477A4.072 4.072 0 012.8 9.713v.052a4.105 4.105 0 003.292 4.022 4.095 4.095 0 01-1.853.07 4.108 4.108 0 003.834 2.85A8.233 8.233 0 012 18.407a11.616 11.616 0 006.29 1.84"
						></path>
					</svg>
				</a>
				<a
					href="https://github.com/RickinShah"
					class="text-gray-400 transition-colors hover:text-teal-400"
				>
					<span class="sr-only">GitHub</span>
					<svg class="h-4 w-4 sm:h-5 sm:w-5" fill="currentColor" viewBox="0 0 24 24">
						<path
							fill-rule="evenodd"
							d="M12 2C6.477 2 2 6.484 2 12.017c0 4.425 2.865 8.18 6.839 9.504.5.092.682-.217.682-.483 0-.237-.008-.868-.013-1.703-2.782.605-3.369-1.343-3.369-1.343-.454-1.158-1.11-1.466-1.11-1.466-.908-.62.069-.608.069-.608 1.003.07 1.531 1.032 1.531 1.032.892 1.53 2.341 1.088 2.91.832.092-.647.35-1.088.636-1.338-2.22-.253-4.555-1.113-4.555-4.951 0-1.093.39-1.988 1.029-2.688-.103-.253-.446-1.272.098-2.65 0 0 .84-.27 2.75 1.026A9.564 9.564 0 0112 6.844c.85.004 1.705.115 2.504.337 1.909-1.296 2.747-1.027 2.747-1.027.546 1.379.202 2.398.1 2.651.64.7 1.028 1.595 1.028 2.688 0 3.848-2.339 4.695-4.566 4.943.359.309.678.92.678 1.855 0 1.338-.012 2.419-.012 2.747 0 .268.18.58.688.482A10.019 10.019 0 0022 12.017C22 6.484 17.522 2 12 2z"
							clip-rule="evenodd"
						></path>
					</svg>
				</a>
				<a
					href="https://www.linkedin.com/in/rickin-shah"
					class="text-gray-400 transition-colors hover:text-teal-400"
				>
					<span class="sr-only">LinkedIn</span>
					<svg class="h-4 w-4 sm:h-5 sm:w-5" fill="currentColor" viewBox="0 0 24 24">
						<path
							d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z"
						></path>
					</svg>
				</a>
			</div>
		</footer>
	</div>
</main>

<style>
	:global(html) {
		scroll-behavior: smooth;
	}

	:global(body) {
		font-family: 'Montserrat', sans-serif;
	}

	h1,
	h2,
	h3,
	h4,
	h5,
	h6 {
		font-family: 'Space Grotesk', sans-serif;
	}

	.bg-grid-pattern {
		background-image:
			linear-gradient(to right, rgba(255, 255, 255, 0.05) 1px, transparent 1px),
			linear-gradient(to bottom, rgba(255, 255, 255, 0.05) 1px, transparent 1px);
		background-size: 20px 20px;
	}

	@keyframes float {
		0% {
			transform: translateY(0px);
		}
		50% {
			transform: translateY(-10px);
		}
		100% {
			transform: translateY(0px);
		}
	}

	@keyframes pulse {
		0%,
		100% {
			opacity: 0.4;
		}
		50% {
			opacity: 0.2;
		}
	}

	@keyframes gradient {
		0% {
			background-position: 0% 50%;
		}
		50% {
			background-position: 100% 50%;
		}
		100% {
			background-position: 0% 50%;
		}
	}

	@keyframes blob {
		0% {
			transform: translate(0px, 0px) scale(1);
		}
		33% {
			transform: translate(20px, -30px) scale(1.1);
		}
		66% {
			transform: translate(-15px, 15px) scale(0.9);
		}
		100% {
			transform: translate(0px, 0px) scale(1);
		}
	}

	@keyframes fade-in {
		from {
			opacity: 0;
			transform: translateY(15px);
		}
		to {
			opacity: 1;
			transform: translateY(0);
		}
	}

	@keyframes floating {
		0% {
			transform: translateY(0) translateX(0);
			opacity: 0.3;
		}
		50% {
			transform: translateY(-15px) translateX(5px);
			opacity: 0.7;
		}
		100% {
			transform: translateY(0) translateX(0);
			opacity: 0.3;
		}
	}

	.animate-blob {
		animation: blob 7s infinite;
	}

	.animate-gradient {
		background-size: 300% 300%;
		animation: gradient 3s ease infinite;
	}

	.animate-float {
		animation: float 6s ease-in-out infinite;
	}

	.animate-pulse {
		animation: pulse 3s ease-in-out infinite;
	}

	/* Responsive Adjustments */
	@media (max-width: 768px) {
		/* Header */
		header {
			height: 56px;
		}
		nav ul {
			gap: 1rem;
		}
		nav a {
			font-size: 0.875rem;
		}

		/* Hero Section */
		#about {
			padding-top: 4rem;
			min-height: auto;
		}
		#about > div {
			flex-direction: column;
			text-align: center;
		}
		#about .animate-float {
			margin-bottom: 1.5rem;
		}
		#about h1 {
			font-size: 2.5rem;
		}
		#about p {
			font-size: 0.9375rem;
		}
		#about .flex-wrap {
			justify-content: center;
		}

		/* Projects Section */
		#projects {
			padding-bottom: 3rem;
		}
		#projects h2 {
			font-size: 1.875rem;
		}
		#projects p {
			font-size: 0.875rem;
		}
		#projects .space-y-10 > div {
			margin-left: 1rem;
			margin-right: 1rem;
		}

		/* Tech Stack Section */
		#tech {
			padding-top: 3rem;
			padding-bottom: 3rem;
		}
		#tech h2 {
			font-size: 1.875rem;
		}
		#tech p {
			font-size: 0.875rem;
		}
		#tech .grid {
			grid-template-columns: repeat(2, minmax(0, 1fr));
			gap: 1.5rem;
		}

		/* Contact CTA */
		section.py-16 {
			padding-top: 3rem;
			padding-bottom: 3rem;
		}
		section.py-16 h2 {
			font-size: 1.5rem;
		}
		section.py-16 p {
			font-size: 0.875rem;
		}

		/* Footer */
		footer {
			padding-top: 1.5rem;
			padding-bottom: 1.5rem;
		}
		footer p {
			font-size: 0.8125rem;
		}
	}

	@media (min-width: 640px) and (max-width: 1024px) {
		/* Hero Section */
		#about .flex-col {
			gap: 2rem;
		}
		#about .animate-float img {
			height: 14rem;
			width: 14rem;
		}

		/* Tech Stack Section */
		#tech .grid {
			grid-template-columns: repeat(3, minmax(0, 1fr));
		}
	}

	@media (min-width: 1024px) {
		/* Tech Stack Section */
		#tech .grid {
			grid-template-columns: repeat(5, minmax(0, 1fr));
		}
	}
</style>
