<script>
    export let text;
    export let rating;
</script>
<svg height="100" width="100">
    <circle r={rating*3} cx="50" cy="50%" />
    <text x="50%" y="90%" text-anchor="moddle">{text}</text>
</svg>