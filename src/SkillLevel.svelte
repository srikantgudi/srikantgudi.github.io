<script>
	export let rating = 50;
	export let label = "HTML";
</script>
<style>
	.wrapper {
		display:flex;
		flex-flow:column;
		align-items:flex-start;
		background-color: lightcyan;
		width:205px;
		padding: 2px;
		margin-bottom: 4px;
	}
</style>
<div class="wrapper">
	<div>
		{label}
	</div>
	<div>
		<svg height="20" width="200">
			<rect x="0" y="0" rx="3" ry="3" width="100%" height="100%" fill="lightblue" stroke="navy" />
			<rect x="1%" y="10%" rx="5" width={`${rating}%`} height="80%" fill="navy" />
		</svg>		
	</div>
</div>

