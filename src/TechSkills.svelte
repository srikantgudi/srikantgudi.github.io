<script>
  import { Card, CardTitle, CardText, Chip, ListItem } from 'svelte-materialify';

  import {data} from './data/data';
</script>

<Card class="card">
  <CardTitle class="card-title">
    Technical Skills
  </CardTitle>

  <CardText class="card-details content-text">
    {#each Object.keys(data.skills) as grouptitle}
      <Card>
        <CardTitle>{grouptitle.toUpperCase()}</CardTitle>
        <CardText>
          {#each data.skills[grouptitle] as skill}
            <Chip style="background-color: blue!important">{skill}</Chip>
          {/each}
        </CardText>
      </Card>
    {/each}
  </CardText>
</Card>
