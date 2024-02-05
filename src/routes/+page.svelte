<script lang="ts">
	import CtaButtons from '../components/cta-buttons.svelte';
	import Rejection from '../components/rejection.svelte';

	const rejection = [
		{ message: 'Estas segura, de que no quieres ser mi valentin?', image: '/think.gif' },
		{ message: 'Como que no quieres? ', image: '/amazed.gif' },
		{ message: 'No aceptare un NO por respuesta', image: '/duck-knife.png' },
		{ message: 'Lo siento, me altere, entonces no quieres?', image: '/calm.gif' },
		{ message: 'Andale, no seas mala, acepta ser mi valentin', image: '/please.gif' }
	];
	let rejectionIndex = 0;
	let rejected = false;
	let accepted = false;

	const handleRejection = () => {
		if (!rejectionIndex && !rejected) {
			rejected = true;
		} else {
			rejectionIndex++;
		}
	};

	const handleAccept = () => {
		accepted = true;
	};
</script>

<main style="height: 100vh; width: 100vw; background-image: url(/bg-dots.svg);">
	<div
		style="display: flex; flex-direction: column; gap: 1rem; justify-content: center; align-items: center; height: inherit; width: inherit;"
	>
		{#if !rejected && !accepted}
			<img
				src="/my-valentine.jpg"
				alt="My Valentine"
				style="width: 300px; height: 311px; object-fit: cover; "
			/>
			<p>&#8195</p>
		{/if}
		{#if accepted}
			<img
				src="/love.gif"
				alt="My Valentine"
				style="width: 400px; height: 311px; object-fit: cover; "
			/>
			<p
				style="color: #fff; font-size: 2rem; text-align: center; padding: 1rem; background: #000111; border-radius: 1rem;"
			>
				SIUUUUU, sabria que dirias que si 😉
			</p>
		{/if}
		{#if rejected && !accepted}
			<Rejection rejection={rejection[rejectionIndex]} />
		{/if}

		<CtaButtons
			{handleAccept}
			{handleRejection}
			hideRejectedButton={rejectionIndex === rejection.length - 1 || accepted}
			hideAcceptedButton={accepted}
		/>
	</div>
</main>
