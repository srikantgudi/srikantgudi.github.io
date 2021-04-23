<script>
	export let width = 600;
	export let r
	export let txt
	export let bg = 'lightgrey'
	export let clr = 'whitesmoke'
</script>
<svg height='40' width={width}>
	<rect x='0' y='0' width='90%' height='100%' fill={bg} stroke='grey' />
	<rect x='2' y='5%' width={`${r}%`} height='90%' fill={clr} />
	<text x='5%' y='60%' font-size='16' fill='blue'>{txt}</text>
</svg>