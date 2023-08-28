<div class="flex flex-col items-center pt-5 space-y-5">
	{#each iconData as {svg, bg, tooltip}, i}
		<div style="--bg:{bg}" class={`icon-button w-[48px] h-[48px] rounded-[50%] flex justify-center items-center cursor-pointer hover:rounded-[32%] bg-[#35363c]`}
		>
			{@html svg}
			<div class="tooltip">
				{tooltip}
			</div>
		</div>
	{/each}
</div>
<script> 
	export let iconData;
</script>
<style >
		.icon-button {
		transition: all 0.3s linear;
		position: relative ;
	}

	.icon-button:hover {
		background-color: var(--bg);
	}

	.icon-button:hover :global(svg) {
		fill: white;
	}

	.tooltip {
		display: none;
		position: absolute;
		bottom: 20%;
		left: 125%;
		padding: 5px 10px;
		background-color: rgba(0, 0, 0, 0.8);
		color: white;
		border-radius: 4px;
		opacity: 0;
		pointer-events: none;
		transition: opacity 0.2s ease-in-out;
	}

	.icon-button:hover .tooltip {
		display: block;
		opacity: 1;
	}
</style>