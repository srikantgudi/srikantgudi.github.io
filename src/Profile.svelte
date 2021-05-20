<script>
  import { Container, Row, Col, Card, CardTitle, ListItem } from 'svelte-materialify';
  import {data} from './data/data';
</script>
<Card>
  <CardTitle class="section-title">
    Profile
  </CardTitle>
  <div>
    <ul>
      {#each data.profile as text}
        <ListItem class="content-text">
          {text}
        </ListItem>
      {/each}
    </ul>
  </div>
</Card>