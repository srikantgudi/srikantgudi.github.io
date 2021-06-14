<script>
  import { Card, CardTitle, CardText, Chip, ListItem } from 'svelte-materialify';

  import {data} from './data/data';
  import {currentComp} from './store';

  const setComp = (n) => {
    $currentComp = n
  }
</script>

<Card class="card">
  <div on:click={() => setComp(2)}>
    <CardTitle class="card-title">
      Technical Skills
    </CardTitle>
  </div>

  <div class="card-details" class:active={$currentComp === 2}>
    <CardText class="content-text">
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
  </div>
</Card>
