<script>
	export let rating;
	export let text;
</script> 

<svg height="40" width="180">
	<rect x="0" y="0" width="100%" height="30" fill="grey" stroke="grey" />
	<rect x="1" y="1" width={`${rating}%`} height="28" fill="#ddf" />

	<text x="5" y="50%" font-size="16">{text}</text>
</svg>
