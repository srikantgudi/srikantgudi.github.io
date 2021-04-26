<script>
  import {data} from './data/data';
  let appname = '';
</script>
<div class="panel">
  <div class="title panel-title section lite">
    Demo Apps
  </div>
  <div class="panel-content">
    {#each data.demoapps as app}
      <div class="demoapp content-item">
        <div>
          <a class="demoapp-title" target="_blank" href={`https://${app.appname}.netlify.app`}>
            {app.title}
          </a>
          <div class="appinfo">
            <div class:active={app.appname=appname}>
              <div>Technology: {app.technology}</div>
              <div>{app.description}</div>
            </div>
          </div>
        </div>
      </div>
    {/each}
  </div>
</div>