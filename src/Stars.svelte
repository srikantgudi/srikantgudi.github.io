<script>
	export let nfill = 0;
  const fillclr = 'olive';
	let clr = nfill ? fillclr : '#eee';
</script>
{#each {length:10} as _,l}
  <svg height="20" width="20" style="margin: 0 1px;">
  	<path d="M0 20 L6,12 0,10 6,8 10,0 14,8 20,10 14,12 20,20 10,14 0,20 z" fill={l < nfill ? clr : '#f7f7f7'} stroke={fillclr} />
  </svg>
{/each}
