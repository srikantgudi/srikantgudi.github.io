<script>
  export let text = 'testing text'
  export let level = 1
  let levels = [
    '5%',
    '15%',
    '25%',
    '35%',
    '45%',
    '55%',
    '65%',
    '75%',
    '85%',
    '95%',
  ]
  let clr = [
    'aliceblue',
    'lightyellow',
    'lightcyan',
    'lightblue',
    'teal',
    'goldenrod',
    'orange',
    'brown',
    '#900',
    'maroon',
  ]
</script>

<svg height="50" width="160" style="margin:2px 4px;box-shadow: 0 0 2px #666">
  {#each levels as lvl, l}
    <rect
      x={l * 16 + 1}
      y="1"
      width="20"
      height="18"
      stroke="grey"
      fill={clr[l]} />
    <text x={l * 16 + 5} y="14" font-size="8" fill={l < 7 ? '#000' : '#f9f9f9'}>
      {(l + 1).toString()}
    </text>
  {/each}
  <text
    x="70"
    y="47"
    font-size="10"
    font-family="Comic Sans MS"
    text-anchor="middle">
    {text}
  </text>
  <circle r="2" cx="70" cy="35" />
  <line x1="70" y1="35" x2={levels[level - 1]} y2="25" stroke="#666" />
</svg>
