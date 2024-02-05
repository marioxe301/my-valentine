<script lang="ts">
	import { fade } from 'svelte/transition';

	export let rejection: { message: string; image: string };
	export let index: number;
</script>

{#key index}
	<div
		style="display: flex; flex-direction: column; gap: 1rem; justify-content: center; align-items: center;"
		in:fade={{ duration: 300 }}
	>
		<img
			src={rejection.image}
			alt="Rejection"
			style="width: 100%; height: 300px; object-fit: contain;"
		/>
		<p
			style="color: #fff; font-size: 2rem; text-align: center; padding: 1rem; background: #000111; border-radius: 1rem;"
		>
			{rejection.message}
		</p>
	</div>
{/key}
