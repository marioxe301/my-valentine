<script lang="ts">
	export let handleAccept: () => void;
	export let handleRejection: () => void;
	export let hideRejectedButton: boolean;
	export let hideAcceptedButton: boolean;
</script>

<div style="display: flex; flex-wrap: wrap; justify-content: center; gap: 2rem;">
	{#if !hideAcceptedButton}
		<button
			on:click={handleAccept}
			style="border: none; background: chartreuse; width: fit-content; ;min-width: 100px; height: 50px; border-radius: 3rem; padding-inline: 1rem; box-sizing: content-box;"
			><span
				style="color: #000111; font-weight: bolder; font-size: 2rem; text-transform: uppercase;"
				>Si quiero</span
			></button
		>
	{/if}
	{#if !hideRejectedButton}
		<button
			style="border: none; background: crimson; width: fit-content; ;min-width: 100px; height: 50px; border-radius: 3rem; padding-inline: 1rem; box-sizing: content-box;"
			on:click={handleRejection}
			><span style="color: #fff; font-weight: bolder; font-size: 2rem; text-transform: uppercase;"
				>No quiero</span
			></button
		>
	{/if}
</div>
