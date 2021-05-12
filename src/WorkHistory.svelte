<script>
  import { Container, Row, Col, Chip, Card, CardTitle, CardSubtitle, CardText, ListItem } from 'svelte-materialify';
  import {data} from './data/data';
</script>

<Card>
  <CardTitle class="section-title">
    Work Experience
  </CardTitle>
</Card>
{#each data.exp as xp}
  <Card>
    <CardTitle>
      {xp.jobTitle}::{xp.dates}
    </CardTitle>
    <CardSubtitle>
      {xp.org}
    </CardSubtitle>
    <CardText>
      Technologies used: <span class="technology">{xp.technology}</span>
    </CardText>
    <CardText>
      <details>
        <summary>Details:</summary>
        <ul>
          {#each xp.content as xptxt}
            <li>{xptxt}</li>
          {/each}
        </ul>
      </details>
    </CardText>
  </Card>
{/each}