<script>
    export let rating;
    const clr = rating < 7 ? 'grey' : rating < 8 ? 'teal' : 'navy'; 
    const maxwid = 140
    $: wid = (maxwid / 10) * rating
</script>
<svg height="20" width={maxwid+1}>
    <rect x="1" y="1" width={maxwid} height={19} fill={'#dddddd'} stroke={clr} />
    <rect x="1" y="1" width={wid} height={18} fill={clr} />
    <text x="50" y="10">{rating}</text>
</svg>
