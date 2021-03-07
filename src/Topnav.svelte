<div class="topnav">
  <div class="pageTitle">Srikant Gudi</div>
  <div class="contact">
    <div class="contact-item">Bengaluru, India</div>
    <div class="contact-item">srikantgudi@gmail.com</div>
    <div class="contact-item">+91-829-665-6336</div>
  </div>
  <div class="position-title">
    <svg height="30" width="auto">
      <text id="postitle" x="50%" y="20" class="pos" text-anchor="middle" font-size="20px">
        Senior Frontend Professional
        <animate attributeName="fill"
          values="blue;lightblue;navy;lightblue;blue"
          begin="0" dur="10s" repeatCount="indefinite" />
      </text>
    </svg>
</div>
</div>

<style>
.pageTitle {
  font-size: 24px;
  text-transform: uppercase;
  text-align: center;
  margin-bottom: 10px;
  font-family: Orbitron;
}
.topnav {
  margin: 0 auto 10px;
  background-color: #eeeeee;
  box-shadow: 0 4px 2px #999;
  border-radius: 0 0 20px 20px;
  padding: 10px 20px;
}
.contact {
  display: flex;
  flex-flow: row wrap;
  align-items: center;
  gap: 10px;
  width: 60vw;
  margin: 0 auto;
}
.contact-item {
  padding: 10px;
  width: 30%;
}
.position-title {
  padding: 10px;
  font-family: Righteous;
}
@media screen and (max-width: 480px) {
  #postitle {
    font-size: 90%;
  }
  .topnav {
    padding: 10px 0;
  }
  .pageTitle {
    font-size: 100%;
  }
  .contact {
    flex-flow: column;
    gap: 0;
    text-align: center;
    padding: 0;
  }
  .contact-item {
    font-size: 80%;
    width: 100%;
  }
}
</style>
