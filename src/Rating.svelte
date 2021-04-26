<script>
	export let width = 600;
	export let r
	export let txt
	export let bg = 'lightgrey'
	export let clr = 'whitesmoke'
</script>
<svg height='30' width={width}>
	<defs>
		<linearGradient id="bar" x1="0%" x2="100%" y1="0%" y2="0%">
			<stop offset="0%" stop-color="whitesmoke" />
			<stop offset="100%" stop-color="darkgrey" />
		</linearGradient>
	</defs>
	<rect x='0' ry="4" rx="10" y='0' width='90%' height='100%' fill={bg} stroke='grey' />
	<rect x='2' y='5%' width={`${r}%`} height='90%' fill="url(#bar)" />
	<text x='10' y='60%' font-size='16' fill='navy'>{txt}</text>
</svg>