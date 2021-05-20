<script>
  import { Row, Col, Card, CardTitle, CardSubtitle, CardText, ListItem } from 'svelte-materialify';

  import {data} from './data/data';
  let appname = '';
</script>
<Card>
  <CardTitle class="section-title">
    Demo Apps
  </CardTitle>
</Card>
<Row noGutters>
{#each data.demoapps as app}
  <Col md={6} sm={12}>
    <Card class="mt-2 mb-2 mr-2">
      <CardTitle>
        <a class="demoapp-title" target="_blank" href={`https://${app.appname}.netlify.app`}>
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
  </Col>
{/each}
</Row>
