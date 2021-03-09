<div class="topnav">
  <div class="pageTitle">Srikant Gudi</div>
  <div class="contact">
    <div class="contact-item">Bengaluru, India</div>
    <div class="contact-item">srikantgudi@gmail.com</div>
    <div class="contact-item">+91-829-665-6336</div>
  </div>
  <div class="position-title">
    Senior Frontend Professional
  </div>
</div>
<div class="note">(Hover on each section to see effect)</div>

<style>
.note {
  display: flex;
  flex-flow: row;
  align-items: center;
  justify-content: center;
  font-family: sans-serif;
  font-size:10px;
  font-style:italic;
}
.pageTitle {
  font-size: 24px;
  text-transform: uppercase;
  text-align: center;
  padding-top: 10px;
  font-family: Orbitron;
}
.topnav {
  display: flex;
  flex-flow: row wrap;
  justify-content: center;
  margin: 0 auto 10px;
  padding: 10px;
  width: 90vw;
  background-color: #eeeeee;
  box-shadow: 0 4px 2px #999;
  border-radius: 0 0 20px 20px;
}
.contact {
  display: flex;
  flex-flow: row wrap;
  align-items: center;
  gap: 10px;
  margin: 0 auto;
}
.contact-item {
  font-family: Montserrat;
  margin: 4px;
  min-width: 25%;
  text-align: center;
}
.position-title {
  font-family: Righteous;
  font-weight: 600;
  text-align: center;
}
@media screen and (max-width: 480px) {
  #postitle {
    font-size: 90%;
  }
  .topnav {
    display: flex;
    flex-flow: column;
    width: 90%;
    text-align: center;
  }
  .contact, .pageTitle {
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
