<script>
  import { Container, Row, Col, Chip, Card, CardTitle, CardSubtitle, CardText, ListItem } from 'svelte-materialify';
  import {data} from './data/data';
  import {currentComp} from './store';

  const setComp = (n) => {
    $currentComp = n
  }
</script>

<div class='exp'>
  <Card class="card">
    <div on:click={() => setComp(4)}>
      <CardTitle class="card-title">
        Work Experience
      </CardTitle>
    </div>
    <div class="card-details" class:active={$currentComp === 4}>
      <CardText>
        {#each data.exp as xp}
          <Card class="mt-2 mb-2">
            <CardTitle class="demoapp-title">
              <div>{xp.jobTitle}</div>
            </CardTitle>
            <CardSubtitle class="content-title">
              {xp.dates} :: {xp.org}
            </CardSubtitle>
            <CardText class="content-text">
              <div>Technologies used: {xp.technology}</div>
              <details>
                <summary>Details:</summary>
                <div>
                  <ul>
                    {#each xp.content as xptxt}
                      <li>{xptxt}</li>
                    {/each}
                  </ul>
                </div>
              </details>
            </CardText>
          </Card>
        {/each}
      </CardText>
    </div>
  </Card>
</div>