<script lang="ts">
	export let rejection: { message: string; image: string };
</script>

<div
	style="display: flex; flex-direction: column; gap: 1rem; justify-content: center; align-items: center;"
>
	<img
		src={rejection.image}
		alt="Rejection"
		style="width: 100%; height: 300px; object-fit: contain;"
		loading="lazy"
	/>
	<p
		style="color: #fff; font-size: 2rem; text-align: center; padding: 1rem; background: #000111; border-radius: 1rem;"
	>
		{rejection.message}
	</p>
</div>
