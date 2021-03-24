<script>
	export let text;
	export let level = 1;
	export let width = 220;
	export let ht = 20;
	let wid = width > 250 ? 250 : width
</script>
<svg height={ht} width={wid}>
	<rect x="10" y="5" width={wid} height={ht} stroke="navy" fill="#caf0f8" />
	<rect x="10" y="5" width={level*wid/10} height={ht*0.8} fill="#023e8a" />
	<text x="20" y={ht/2+(ht/5)} fill="white">{text}</text>
</svg>