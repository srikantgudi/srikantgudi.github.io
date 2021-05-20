<script>
  import { Container, Row, Col, Chip, Card, CardTitle, CardSubtitle, CardText, ListItem } from 'svelte-materialify';
  import {data} from './data/data';
</script>

<Card>
  <CardTitle class="section-title">
    Work Experience
  </CardTitle>
</Card>
<Row>
{#each data.exp as xp}
  <Col md={6} sm={12}>
    <Card class="mt-2 mb-2">
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
  </Col>
{/each}
</Row>
