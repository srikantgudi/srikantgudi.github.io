<script>
  import Panel from './Panel.svelte'

  let profiles = [
    'Senior software professional with over 20 years of experience',
    '2005 - 2013: Web development experience using PHP, MySQL',
    '2014 onwards into UI development. Skills used Angular, React, Svelte, Stencil, NodeJs, MySql',
    'Can create wire-frames, POCs',
  ]
</script>

<style>
  .text {
    font-family: Montserrat;
    font-size: 16px;
  }

  @media screen and (max-width: 719px) {
    .text {
      font-size: 90%;
    }
  }
</style>

<Panel>
  <div slot="header">Profile</div>
  <div slot="content">
    <ul class="text">
      {#each profiles as line}
        <li>{line}</li>
      {/each}
    </ul>
  </div>
</Panel>
