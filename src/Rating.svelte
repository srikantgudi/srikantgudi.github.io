<script>
	export let text;
	export let rating = 5;
	export let clr="#ccc";
</script>

<svg height="120" width="100">
	<circle r={rating/2*10} cx="50" cy="50" fill={clr} />
	<text x="50%" y="90%" text-anchor="middle">{text}</text>
	<rect x="1" y="1" width="98%" height="98%" fill="transparent" stroke="grey" />
</svg>