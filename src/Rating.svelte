<script>
	export let r
	export let txt
	export let bg = 'lightgrey'
	export let clr = 'whitesmoke'
</script>
<svg height='40' width='200'>
	<rect x='0' y='0' width='90%' height='100%' fill={bg} stroke='blue' />
	<rect x='1%' y='5%' width={`${r}%`} height='90%' fill={clr} />
	<text x='5%' y='60%' font-size='16' fill='blue'>{txt}</text>
</svg>