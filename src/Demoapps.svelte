<script>
  import { Row, Col, Chip, Card, CardTitle, CardSubtitle, CardText, CardActions, ListItem } from 'svelte-materialify';

  import {data} from './data/data';
  import {currentComp} from './store';

  let appname = '';
  
  let currentApp = data.demoapps[0];

  const setComp = (n) => {
    $currentComp = n
  }

  const setApp = (app) => {
    currentApp = app
  }
</script>

<style>
  .demoapps {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 1em;
  }
  .apptitle {
    cursor: pointer;
  }
</style>

<Card class='exp card'>
  <div on:click={() => setComp(3)}>
    <CardTitle class="card-title">
      Demo Apps
    </CardTitle>
  </div>

  <div class="card-details" class:active={$currentComp === 3}>
    <CardText>
      <Row class="demoapps">
        {#each data.demoapps as app}
          <Col md={6} sm={12}>
            <Card style="height:13em">
              <CardTitle>
                {app.title}
                <Chip outlined class="ma-2 link secondary-text">
                  <a class="link secondary-text" target="_blank" href={`https://${app.appname}.netlify.app`}>
                    View
                  </a>
                </Chip>
              </CardTitle>
              <CardSubtitle>{app.technology}</CardSubtitle>
              <CardText>
                <div>
                  {app.description}
                </div>
                <div>
                </div>
              </CardText>
            </Card>
          </Col>
        {/each}
      </Row>
    </CardText>
  </div>
</Card>