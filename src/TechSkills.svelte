<script>
  import { Container, Row, Col, Chip, Card, CardTitle, ListItem } from 'svelte-materialify';

  import {data} from './data/data';
  import Rating from './Rating.svelte';
</script>

<Card>
  <CardTitle class="section-title">
    Technical Skills
  </CardTitle>

  <div class="panel-content tech-skills">
    <Row>
      {#each Object.keys(data.skills) as grouptitle}
        <Col>
          <CardTitle>{grouptitle.toUpperCase()}</CardTitle>
          <Col>
            {#each data.skills[grouptitle] as skill}
              <Chip class="ma-1">{skill}</Chip>
            {/each}
          </Col>
        </Col>
      {/each}
    </Row>
  </div>
</Card>
