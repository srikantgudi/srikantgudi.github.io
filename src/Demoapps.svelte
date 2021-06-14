<script>
  import { Row, Col, Card, CardTitle, CardSubtitle, CardText, ListItem } from 'svelte-materialify';

  import {data} from './data/data';
  let appname = '';
</script>

<Card class='exp card'>
  <CardTitle class="card-title">
    Demo Apps
  </CardTitle>
  <CardText class="card-details">
    {#each data.demoapps as app}
      <Card>
        <CardTitle>
          <a target="_blank" href={`https://${app.appname}.netlify.app`}>
            {app.title}
          </a>
        </CardTitle>
        <CardSubtitle class="content-text">
          <div>Technology: {app.technology}</div>
        </CardSubtitle>
        <CardText class="content-text">
          <div>{app.description}</div>
        </CardText>
      </Card>
    {/each}
  </CardText>
</Card>