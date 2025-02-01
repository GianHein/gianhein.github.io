<script>
	import * as m from '$lib/paraglide/messages.js';

	import Nav from '$components/Nav.svelte';

	const technologies = [
		{
			name: 'atom',
			url: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/atom/atom-original.svg'
		},
		{
			name: 'azure',
			url: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/azure/azure-original.svg'
		},
		{
			name: 'bash',
			url: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/bash/bash-original.svg'
		},
		{
			name: 'bootstrap',
			url: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/bootstrap/bootstrap-original.svg'
		},
		{
			name: 'chrome',
			url: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/chrome/chrome-original.svg'
		},
		{
			name: 'cplusplus',
			url: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/cplusplus/cplusplus-original.svg'
		},
		{
			name: 'csharp',
			url: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/csharp/csharp-original.svg'
		},
		{
			name: 'css3',
			url: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg'
		},
		{
			name: 'dart',
			url: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/dart/dart-original.svg'
		},
		{
			name: 'debian',
			url: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/debian/debian-original.svg'
		},
		{
			name: 'discordjs',
			url: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/discordjs/discordjs-original.svg'
		},
		{
			name: 'dotnetcore',
			url: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/dotnetcore/dotnetcore-original.svg'
		},
		{
			name: 'electron',
			url: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/electron/electron-original.svg'
		},
		{
			name: 'eslint',
			url: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/eslint/eslint-original.svg'
		},
		{
			name: 'express',
			url: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/express/express-original.svg'
		},
		{
			name: 'filezilla',
			url: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/filezilla/filezilla-plain.svg'
		},
		{
			name: 'firefox',
			url: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/firefox/firefox-original.svg'
		},
		{
			name: 'flutter',
			url: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/flutter/flutter-original.svg'
		},
		{ name: 'git', url: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/git/git-original.svg' },
		{
			name: 'github',
			url: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/github/github-original.svg'
		},
		{ name: 'go', url: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/go/go-original.svg' },
		{
			name: 'godot',
			url: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/godot/godot-original.svg'
		},
		{
			name: 'gradle',
			url: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/gradle/gradle-original.svg'
		},
		{
			name: 'heroku',
			url: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/heroku/heroku-original.svg'
		},
		{
			name: 'html5',
			url: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg'
		},
		{
			name: 'ifttt',
			url: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/ifttt/ifttt-original.svg'
		},
		{
			name: 'intellij',
			url: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/intellij/intellij-original.svg'
		},
		{
			name: 'java',
			url: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/java/java-original.svg'
		},
		{
			name: 'javascript',
			url: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg'
		},
		{
			name: 'jetbrains',
			url: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/jetbrains/jetbrains-original.svg'
		},
		{
			name: 'latex',
			url: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/latex/latex-original.svg'
		},
		{
			name: 'linkedin',
			url: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/linkedin/linkedin-original.svg'
		},
		{
			name: 'linux',
			url: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/linux/linux-original.svg'
		},
		{ name: 'lua', url: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/lua/lua-original.svg' },
		{
			name: 'markdown',
			url: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/markdown/markdown-original.svg'
		},
		{
			name: 'materialui',
			url: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/materialui/materialui-original.svg'
		},
		{
			name: 'mongodb',
			url: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mongodb/mongodb-original.svg'
		},
		{
			name: 'moodle',
			url: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/moodle/moodle-original.svg'
		},
		{
			name: 'mysql',
			url: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mysql/mysql-original.svg'
		},
		{
			name: 'nextjs',
			url: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nextjs/nextjs-original.svg'
		},
		{
			name: 'nginx',
			url: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nginx/nginx-original.svg'
		},
		{
			name: 'nodejs',
			url: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nodejs/nodejs-original.svg'
		},
		{
			name: 'npm',
			url: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/npm/npm-original-wordmark.svg'
		},
		{
			name: 'opengl',
			url: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/opengl/opengl-original.svg'
		},
		{
			name: 'processing',
			url: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/processing/processing-original.svg'
		},
		{
			name: 'putty',
			url: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/putty/putty-original.svg'
		},
		{
			name: 'pycharm',
			url: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/pycharm/pycharm-original.svg'
		},
		{
			name: 'python',
			url: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg'
		},
		{
			name: 'raspberrypi',
			url: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/raspberrypi/raspberrypi-original.svg'
		},
		{
			name: 'react',
			url: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/react/react-original.svg'
		},
		{ name: 'sdl', url: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/sdl/sdl-original.svg' },
		{
			name: 'svelte',
			url: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/svelte/svelte-original.svg'
		},
		{
			name: 'tailwindcss',
			url: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/tailwindcss/tailwindcss-original.svg'
		},
		{
			name: 'trello',
			url: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/trello/trello-plain.svg'
		},
		{
			name: 'twitter',
			url: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/twitter/twitter-original.svg'
		},
		{
			name: 'typescript',
			url: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/typescript/typescript-original.svg'
		},
		{
			name: 'ubuntu',
			url: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/ubuntu/ubuntu-plain.svg'
		},
		{ name: 'vim', url: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/vim/vim-original.svg' },
		{
			name: 'visualstudio',
			url: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/visualstudio/visualstudio-plain.svg'
		},
		{
			name: 'vscode',
			url: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/vscode/vscode-original.svg'
		},
		{
			name: 'webstorm',
			url: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/webstorm/webstorm-original.svg'
		}
	];
</script>

<svelte:head>
	<title>Gian Hein - {m.resume_title()}</title>
</svelte:head>

<Nav />

<div class="relative h-[17vh] max-h-64 min-h-24 bg-gradient-to-b from-secondary/50 to-background">
	<div class="mx-auto flex w-full max-w-7xl px-6">
		<h1 class="absolute bottom-0 font-archivo text-4xl md:text-6xl">{m.resume_title()}</h1>
	</div>
</div>

<div class="mx-auto mt-12 flex w-full max-w-7xl px-6 pb-12">
	<div class="flex w-full flex-col gap-8">
		<div class="flex flex-col gap-2">
			<h2 class="block border-b pb-2 text-2xl font-bold">{m.resume_heading_info()}</h2>
			<div class="flex w-full gap-8">
				<div class="flex flex-1 flex-col gap-4">
					<div>
						<h3 class="text-xl font-semibold">{m.resume_info_name()}</h3>
						<p>Gian Hein</p>
					</div>
					<div>
						<h3 class="text-xl font-semibold">{m.resume_info_birth_date_label()}</h3>
						<p>{m.resume_info_birth_date_value()}</p>
					</div>
				</div>
				<div class="flex flex-1 flex-col gap-4">
					<div>
						<h3 class="text-xl font-semibold">{m.resume_info_phone()}</h3>
						<p>+49(0) 176 4313 4806</p>
					</div>
					<div>
						<h3 class="text-xl font-semibold">{m.resume_info_email()}</h3>
						<a class="text-primary underline" href="mailto:gian.hein@gmail.com">
							gian.hein@gmail.com
						</a>
					</div>
				</div>
			</div>
		</div>

		<div class="grid w-full grid-cols-1 gap-8 md:grid-cols-12">
			<div class="col-span-6 row-span-1 flex flex-col gap-4">
				<h2 class="block border-b pb-2 text-2xl font-bold">{m.resume_heading_education()}</h2>
				<div class="flex flex-col-reverse gap-4 md:gap-8">
					<div>
						<p class="text-sm underline">{m.resume_highschool_date()}</p>
						<h3 class="text-xl font-semibold">{m.resume_highschool_name()}</h3>
						<ul class="list-inside list-none pl-6">
							<li class="flex flex-col md:block">
								{m.resume_highschool_degree_label()}: <span class="text-muted-foreground">2,0</span>
							</li>
							<li class="flex flex-col md:block">
								{m.resume_highschool_advanced_courses_label()}: <span class="text-muted-foreground">{m.resume_highschool_advanced_courses()}</span>
							</li>
							<li class="flex flex-col md:block">
								{m.resume_highschool_examination_subjects_label()}:
								<span class="text-muted-foreground">
                  {m.resume_highschool_examination_subjects()}
								</span>
							</li>
						</ul>
					</div>
					<div>
						<p class="text-sm underline">{m.resume_uni_date()}</p>
						<a
							href="https://www.linkedin.com/school/humboldt-university-berlin"
							class="flex items-center gap-4 py-2"
						>
							<img
								class="size-8 rounded-md"
								alt="Humboldt Universität zu Berlin"
								src="https://media.licdn.com/dms/image/v2/D4D0BAQHhqBuy5vs4qQ/company-logo_200_200/company-logo_200_200/0/1665690095621?e=1746057600&v=beta&t=4FVjoSMyoiA2UIIDXXeF8fBlM3j-gm8JLwwF9OhHmBk"
							/>
							<div class="flex flex-col">
								<h3 class="text-sm font-semibold underline">{m.resume_uni_link_name()}</h3>
								<p class="text-xs text-muted-foreground">{m.resume_uni_link_location()}</p>
							</div>
						</a>
						<h3 class="text-xl font-semibold">{m.resume_uni_name()}</h3>
						<p class="text-muted-foreground">{m.resume_uni_degree()}</p>
					</div>
				</div>
			</div>

			<div class="col-span-6 row-span-4 flex flex-col gap-4">
				<h2 class="block border-b pb-2 text-2xl font-bold">{m.resume_heading_work_experience()}</h2>
				<div class="flex flex-col-reverse gap-4 md:gap-8">
					<div>
						<p class="text-sm underline">{m.resume_work_experience_0_date()}</p>
						<h3 class="text-xl font-semibold">{m.resume_work_experience_0_name()}</h3>
						<p class="text-muted-foreground">{m.resume_work_experience_0_description()}</p>
					</div>
					<div>
						<p class="text-sm underline">{m.resume_work_experience_1_date()}</p>
						<a
							href="https://www.linkedin.com/company/sad-stiller-alarm-deutschland-gmbh/"
							class="flex items-center gap-4 py-2"
						>
							<img
								class="size-8 rounded-md"
								alt="Stiller Alarm Deutschland GmbH"
								src="https://media.licdn.com/dms/image/v2/C4D0BAQE9eCh7KQFB2A/company-logo_200_200/company-logo_200_200/0/1631315504782?e=1746057600&v=beta&t=x5bj594CFpzNGGdUuEomzpdBPiKoXWgVqJ5vsopiHj0"
							/>
							<div class="flex flex-col">
								<h3 class="text-sm font-semibold underline">Stiller Alarm Deutschland GmbH</h3>
								<p class="text-xs text-muted-foreground">{m.resume_work_experience_1_company_location()}</p>
							</div>
						</a>
						<h3 class="text-xl font-semibold">{m.resume_work_experience_1_name()}</h3>
						<p class="text-muted-foreground">{m.resume_work_experience_1_description()}</p>
					</div>
					<div>
						<p class="text-sm underline">{m.resume_work_experience_2_date()}</p>
						<a
							href="https://www.linkedin.com/company/sad-stiller-alarm-deutschland-gmbh/"
							class="flex items-center gap-4 py-2"
						>
							<img
								class="size-8 rounded-md"
								alt="Stiller Alarm Deutschland GmbH"
								src="https://media.licdn.com/dms/image/v2/C4D0BAQE9eCh7KQFB2A/company-logo_200_200/company-logo_200_200/0/1631315504782?e=1746057600&v=beta&t=x5bj594CFpzNGGdUuEomzpdBPiKoXWgVqJ5vsopiHj0"
							/>
							<div class="flex flex-col">
								<h3 class="text-sm font-semibold underline">Stiller Alarm Deutschland GmbH</h3>
								<p class="text-xs text-muted-foreground">{m.resume_work_experience_1_company_location()}</p>
							</div>
						</a>
						<h3 class="text-xl font-semibold">{m.resume_work_experience_2_name()}</h3>
						<p class="text-muted-foreground">
            {m.resume_work_experience_2_description()}
						</p>
					</div>
					<div>
						<p class="text-sm underline">{m.resume_work_experience_3_date()}</p>
						<a
							href="https://www.linkedin.com/company/sad-stiller-alarm-deutschland-gmbh/"
							class="flex items-center gap-4 py-2"
						>
							<img
								class="size-8 rounded-md"
								alt="Stiller Alarm Deutschland GmbH"
								src="https://media.licdn.com/dms/image/v2/C4D0BAQE9eCh7KQFB2A/company-logo_200_200/company-logo_200_200/0/1631315504782?e=1746057600&v=beta&t=x5bj594CFpzNGGdUuEomzpdBPiKoXWgVqJ5vsopiHj0"
							/>
							<div class="flex flex-col">
								<h3 class="text-sm font-semibold underline">Stiller Alarm Deutschland GmbH</h3>
								<p class="text-xs text-muted-foreground">{m.resume_work_experience_1_company_location()}</p>
							</div>
						</a>
						<h3 class="text-xl font-semibold">{m.resume_work_experience_3_name()}</h3>
						<p class="text-muted-foreground">
            {m.resume_work_experience_3_description()}
						</p>
					</div>
					<div>
						<p class="text-sm underline">{m.resume_work_experience_4_date()}</p>
						<a
							href="https://www.linkedin.com/company/unternehmensgruppebruederschlau/"
							class="flex items-center gap-4 py-2"
						>
							<img
								class="size-8 rounded-md"
								alt="Brüder Schlau GmbH & Co. KG"
								src="https://media.licdn.com/dms/image/v2/C4E0BAQGHpEemzGa3nQ/company-logo_200_200/company-logo_200_200/0/1630620040055/brder_schlau_gmbh__co_kg_logo?e=1746057600&v=beta&t=W9O-FfDZWHzjX13X6kvXY086U3cVo3rfjLwVkVven0w"
							/>
							<div class="flex flex-col">
								<h3 class="text-sm font-semibold underline">Brüder Schlau GmbH & Co. KG</h3>
								<p class="text-xs text-muted-foreground">{m.resume_work_experience_4_company_location()}</p>
							</div>
						</a>
						<h3 class="text-xl font-semibold">{m.resume_work_experience_4_name()}</h3>
						<p class="text-muted-foreground">
            {m.resume_work_experience_4_description()}
						</p>
					</div>
				</div>
			</div>

			<div class="col-span-6 row-span-2 w-full">
				<div class="flex flex-col gap-2">
					<h2 class="block border-b pb-2 text-2xl font-bold">{m.resume_heading_skills()}</h2>
					<div class="flex flex-wrap gap-4">
						{#each technologies as { name, url }}
							<div class="flex size-10 items-center justify-center rounded-md bg-secondary">
								<img class="size-8 rounded-md" alt={name} src={url} />
							</div>
						{/each}
					</div>
				</div>
			</div>
		</div>
	</div>
</div>
