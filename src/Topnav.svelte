<script>
  import Academic from "./Academic.svelte";
  import App from "./App.svelte";
</script>

<div class="topnav">
  <div class="topnav-title">Srikant Gudi
    <a href="https://www.linkedin.com/in/srikantgudi-blr/" target="_new" ><img height="16" src="https://content.linkedin.com/content/dam/me/business/en-us/amp/brand-site/v2/bg/LI-Bug.svg.original.svg" alt="IN" /></a>
  </div>
  <div class="contact">
    <div class="contact-item">Bengaluru, India</div>
    <div class="contact-item">srikantgudi@gmail.com</div>
    <div class="contact-item">+91 829 665 6336</div>
  </div>
  <div class="position-title">Senior Frontend Engineer</div>
</div>

<style>
  .topnav {
    box-shadow: 0 0 4px #999;
    min-height: 4em;
    min-width: 100%;
    background: linear-gradient(lightblue, aliceblue, lightblue);
    border-radius: 0 0 10px 10px;
    display: flex;
    align-items: center;
    flex-flow: column;
    justify-content: center;
  }
  .topnav-title {
    font-family: Righteous;
    font-size: 32px;
    font-weight: 400;
    text-transform: uppercase;
    color: navy;
    letter-spacing: 2px;
  }
  .contact {
    display: flex;
    flex-flow: row;
    align-items: center;
    justify-content: center;
    font-family: Montserrat;
    text-align: center;
  }
  .contact-item {
    min-width: 27vw;
    cursor: pointer;
  }
  .position-title {
    text-transform: uppercase;
    font-family: Orbitron;
    font-size: 24px;
    font-weight: 600;
    letter-spacing: 1px;
    text-align: center;
    color: blue;
  }
  @media screen and (max-width: 480px) {
    .topnav {
      display: flex;
      flex-flow: column;
      width: 90%;
      text-align: center;
    }
    .contact {
      display: block;
      width: 100%;
      text-align: center;
      padding: 0;
    }
    .contact-item {
      font-size: 80%;
      width: 100%;
    }
    .position-title {
      font-size: 70%;
    }
  }
</style>
