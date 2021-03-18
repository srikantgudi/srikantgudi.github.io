<script>
	export let val;
	let ratings = [];
	
	$: {
		for (let i=0; i < val; i++) {
			ratings = [
				...ratings,
				`<span style="font-size:16px;letter-spacing:2px;color:blue">*</span>`
			]
		}
		for (let i=val; i < 10; i++) {
			ratings = [
				...ratings,
				`<span style="color:grey;">*</span>`
			]
		}
	}
</script>
{@html ratings.join('')}