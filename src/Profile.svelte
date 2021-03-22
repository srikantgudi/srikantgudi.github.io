<script>
  import {data} from './data/data';
</script>
<style>
  li {
    list-style-type: none;
    text-indent: -15px;
    margin-left: 35px;
  }
  li::before {
    content: '\bb\20';
  }
</style>
<div class="resume-section">
  <div class="subsection">
    <div class="subsectiontitle">About me</div>
    <div class="content-text">
      <ul>
        {#each data.profile as text}
        <li>
          {text}
        </li>
        {/each}
      </ul>
    </div>
  </div>
</div>
