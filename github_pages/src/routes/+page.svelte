<script lang="ts">
	import ProjectCard from "$lib/components/ProjectCard.svelte";

	import {normalizeProject, projectInformation} from "$lib/assets/projects";

	const normalizedProjectInformation = projectInformation.map((project) => normalizeProject(project))
</script>

<main class="h-full w-full">
	<div class="h-full w-full flex flex-row">
		<!-- Name and Information -->
		<div class="flex-1 prose prose-h2:m-0 m-16 w-lg">
			<img src="/img/NoImage.png" alt="Profile" class="rounded-3xl"/>
			<h1>Name goes here</h1>
			<h2 class="m-0">Email goes here</h2>

			<div class="divider"></div>

			<p>something here i guess</p>
		</div>

		<div class="flex-none divider divider-horizontal m-0"></div>

		<!-- Projects -->
		<div class="flex-3 flex flex-col">
			<div class="w-full flex justify-center">
				<h1 class="w-max text-5xl m-4"><strong>My Projects</strong></h1>
			</div>

			<div class="divider"></div>

			<div class="w-full p-4 grid grid-flow-row grid-cols-3 gap-4 overflow-y-scroll">
				{#each normalizedProjectInformation as project }
					<ProjectCard {...project}>
						<p>{project.description}</p>
					</ProjectCard>
				{/each}
			</div>
		</div>
	</div>
</main>
