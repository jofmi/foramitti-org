<script lang="ts">
	import Icon from '@iconify/svelte';
	import { getModalStore } from '@skeletonlabs/skeleton';
	import type { Project } from '$lib/types';
	import { marked } from 'marked';
	const modalStore = getModalStore();
	export let project: Project;

	const renderer: any = {
		link(href: any) {
			const link = marked.Renderer.prototype.link.call(this, href);
			return link.replace('<a', "<a target='_blank' class='marked-link'");
		}
	};

	marked.use({ renderer });
</script>

{#if $modalStore[0]}
	<div
		class="w-modal-wide bg-white p-10 rounded-md space-y-2 flex flex-col gap-2"
	>
		<div class="flex flex-row justify-between">
			<h2 class="h2">{project.title}</h2>
			<a href={project.repositoryUrl} target="_blank">
				<Icon
					icon="bi:github"
					class="text-4xl hover:scale-[1.04] duration-100"
				/>
			</a>
		</div>
		<div class="flex flex-wrap gap-2 pb-4" id="modal-tags">
			<span class="px-2 py-1 bg-slate-200 rounded">{project.date}</span>
			{#each project.tags || [] as tag}
				<span class="px-2 py-1 bg-slate-200 rounded">{tag}</span>
			{/each}
		</div>

		{@html marked(project.description)}

		{#if project.images && project.images.length > 0}
			<div class="flex flex-wrap gap-4 pt-6">
				{#each project.images as image}
					<a href={image} target="_blank">
						<img
							src={image}
							alt={project.title}
							class=" h-56 rounded-md object-contain"
						/>
					</a>
				{/each}
			</div>
		{/if}
	</div>
{/if}
