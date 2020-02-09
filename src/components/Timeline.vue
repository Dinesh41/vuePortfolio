<template>
  <div>
    <main>
      <h3>{{ title }}</h3>
      <section class="timeline">
        <ul>
          <li v-for="(info, index) in timeline_data" v-bind:key="index">
            <span></span>
            <div class="data" v-for="(data, index) in info.data" :key="index">{{ data }}</div>
            <div class="year">
              <span>{{ info.yearEnd }}</span>
              <span>{{ info.yearStart }}</span>
            </div>
            <div class="footer" v-if="info.footer != undefined">
              <a v-if="info.footer.github != undefined" :href="info.footer.github">
                <i class="fab fa-github"></i>
              </a>
              <a v-if="info.footer.other != undefined" :href="info.footer.other">
                <i class="fas fa-external-link-square-alt"></i>
              </a>
            </div>
          </li>
        </ul>
      </section>
    </main>
  </div>
</template>
<script>
export default {
  props: {
    title: String,
    timeline_data: Array
  }
};
</script>
<style scoped>
@import url("https://fonts.googleapis.com/css?family=Montserrat");
body {
  background-color: #fff;
}
main,
span::before,
span::after {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "Montserrat", sans-serif;
  color: #fff;
}
.footer {
  text-align: left;
  padding: 5px;
}
.fa-github {
  color: #fff;
}
.fa-external-link-square-alt {
  color: #fff;
  padding-left: 5px;
}
.footer a {
  display: inline;
  padding-left: 3px;
}
@media only screen and (min-width: 320px) {
  main {
    width: 100%;
    height: 100%;
    margin: 0.7em auto;
    padding: 25px;
    background: #2e4a62;
    border-radius: 4px;
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.5);
  }

  .timeline {
    padding: 2px 40px;
  }
  .timeline ul {
    position: relative;
  }
  .timeline ul::before {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    height: 100%;
  }
  .timeline li {
    position: relative;
    margin: 60px 35px;
    width: 100%;
    list-style: none;
    line-height: 25px;
  }
  .timeline li > span {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    left: -12px;
    height: 110%;
    border: 1px solid #fff;
    border-radius: none;
  }
  .timeline li > span::before,
  .timeline li > span::after {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    width: 12px;
    height: 12px;
    border: 3px solid #fff;
    border-radius: 50%;
    left: -6px;
    background: #4e9bfa;
  }
  .timeline li > span::before {
    top: -13px;
  }
  .timeline li > span::after {
    top: 100%;
  }
  .timeline li .data:nth-child(2) {
    font-size: 1em;
    font-weight: bold;
  }
  .timeline li .data {
    text-align: left;
    padding-left: 5px;
  }
  .timeline li .data:nth-child(3) {
    font-size: 0.8em;

    color: #94ff92;
  }
  .timeline li .data:nth-child(4) {
    font-size: 0.8em;

    color: #fffcfc;
    padding-top: 8px;
  }
  .timeline li .year span {
    position: absolute;
    font-size: 0.8em;
    left: -105px;
    width: 80px;
    text-align: right;
  }
  .timeline li .year span:first-child {
    top: -20px;
  }
  .timeline li .year span:last-child {
    top: 100%;
  }
}
@media only screen and (min-width: 768px) {
  main {
    width: 80%;
    height: 100%;
    margin: 1em auto;
    padding: 40px;
    background: #2e4a62;
    border-radius: 4px;
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.5);
  }

  .timeline {
    padding: 5px 45px;
  }
  .timeline ul {
    position: relative;
  }
  .timeline ul::before {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    height: 100%;
  }
  .timeline li {
    position: relative;
    margin: 60px 35px;
    width: 100%;
    list-style: none;
    line-height: 25px;
  }
  .timeline li > span {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    left: -10px;
    height: 110%;
    border: 2px solid #fff;
    border-radius: none;
  }
  .timeline li > span::before,
  .timeline li > span::after {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    width: 14px;
    height: 14px;
    border: 3px solid #fff;
    border-radius: 50%;
    left: -7px;
    background: #4e9bfa;
  }
  .timeline li > span::before {
    top: -15px;
  }
  .timeline li > span::after {
    top: 100%;
  }
  .timeline li .data:nth-child(2) {
    font-size: 1.3em;
    font-weight: bold;
  }
  .timeline li .data {
    text-align: left;
    padding-left: 5px;
  }
  .timeline li .data:nth-child(3) {
    font-size: 1em;
    color: #94ff92;
  }
  .timeline li .data:nth-child(4) {
    font-size: 1em;
    color: #fffcfc;
    padding-top: 8px;
  }
  .timeline li .year span {
    position: absolute;
    font-size: 1em;
    left: -105px;
    width: 80px;
    text-align: right;
  }
  .timeline li .year span:first-child {
    top: -20px;
  }
  .timeline li .year span:last-child {
    top: 100%;
  }
}
</style>
