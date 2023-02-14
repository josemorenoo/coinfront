<script setup>
import Card from "../components/about/Card.vue"
import TextExpander from "../components/about/TextExpander.vue"
import Footer from "../components/Footer.vue"
</script>

<template>
  <div class="about">
    <div class="mission-container">
      <p class="mission-title">Mission</p>
      <p class="large-text">Providing automated analysis of open-source cryptocurrency codebases</p>
      <p class="medium-text">with the goal of discovering price catalysts thru code, and evaluating project viability.
      </p>
      <button class="lets-go-button" @click="$router.push('/')">Let's go!</button>
    </div>
    <img class="ellipse" src="@/assets/ellipse.png" />
    <div class="bottom">
      <TextExpander />
      <div class="roadmap-background">
        <div class="roadmap">
          <p class="future">Our Future</p>
          <div class="card-holder">
            <Card :cardText="'Next step number 01 - Lorem ipsum dolor sit amet consectetur. Eget neque tellus nibh.'" />
            <Card :cardText="'Next step number 02 - Lorem ipsum dolor sit amet consectetur. Eget neque tellus nibh.'" />
            <Card :cardText="'Next step number 03 - Lorem ipsum dolor sit amet consectetur. Eget neque tellus nibh.'" />
          </div>
        </div>
      </div>
      <div class="linebreak"></div>
      <div class="bottom-text">Enjoy our community!</div>
      <div class="button-holder">
        <button class="inverse-button"
          onclick=" window.open('https://twitter.com/coin_commit', '_blank'); return false;">Follow on Twitter</button>
      </div>
    </div>
    <Footer />
  </div>
</template>

<style>
.about {
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding-top: 0rem;
  overflow-y: auto;
  height: 100%;
}

.mission-container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding-top: 96rem;
  padding-bottom: 2rem;
  gap: 3rem;
}

.mission-title {
  width: 75%;

  /* Desktop Header 4 */

  font-family: 'Roboto';
  font-style: normal;
  font-weight: 400;
  font-size: 24px;
  line-height: 150%;
  /* or 36px */

  text-align: center;

  /* F6F8FF */

  color: #F6F8FF;


  /* Inside auto layout */

  flex: none;
  order: 0;
  margin-left: 0rem;
  margin-top: 0rem;
}

.large-text {
  width: 75%;

  font-family: 'Roboto';
  font-style: normal;
  font-weight: 400;
  font-size: 48px;
  line-height: 130%;
  /* or 73px */

  align-items: center;
  text-align: center;

  /* White */

  color: #FFFFFF;


  /* Inside auto layout */

  flex: none;
  order: 1;
  margin-bottom: 0px;
  margin-top: 0px
}

.medium-text {
  width: 75%;

  font-family: 'Roboto';
  font-style: normal;
  font-weight: 400;
  font-size: 28px;
  line-height: 40px;

  align-items: center;
  text-align: center;

  /* White */

  color: #FFFFFF;


  /* Inside auto layout */

  flex: none;
  order: 2;
  margin-bottom: 0px;
  margin-top: 0px
}

.lets-go-button {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;

  width: 14rem;
  height: 3rem;

  /* 2CC3F3 */

  background: #2CC3F3;
  border-radius: 8px;

  /* Inside auto layout */

  flex: none;
  order: 3;
  margin-bottom: 0px;
  margin-top: 0px;
  font-size: 18px;
}

.ellipse {
  margin-bottom: -180px;
  padding-top: 4rem;
  z-index: -1;
  background-size: cover;
  background-position: center;
}

.bottom {
  display: flex;
  flex-direction: column;
  background-color: #120B26;
}

.roadmap-background {
  width: 100%;
  background-color: #120B26;
}

.roadmap {
  padding-left: 10%;
  padding-right: 10%;
  display: flex;
  flex-direction: column;
  padding-bottom: 5rem;
}

.future {
  padding-left: 1rem;
  font-family: 'Roboto';
  font-style: normal;
  font-weight: 400;
  font-size: 32px;
  line-height: 40px;

  display: flex;
  align-items: center;

  color: #6DF8FF;
}

.card-holder {
  display: flex;
  flex-direction: row;
  gap: 3rem;
}

.logo-container {
  height: fit-content;
}

.linebreak {
  background-color: #20254A;
  height: 2px;
}

.bottom-text {
  background-color: #120B26;
  margin-left: auto;
  margin-right: auto;

  font-family: 'Roboto';
  font-style: normal;
  font-weight: 400;
  font-size: 32px;
  line-height: 40px;

  display: flex;
  align-items: center;
  text-align: center;
  padding-top: 4rem;

  color: #FFFFFF;
}

.button-holder {
  padding-top: 3rem;
  padding-bottom: 6rem;
}

.inverse-button {
  width: 14%;
  margin-left: auto;
  margin-right: auto;

  box-sizing: border-box;
  border: 1px solid #2CC3F3;
  background-color: #120B26;
  border-radius: 8px;

  font-family: 'Roboto';
  font-style: normal;
  font-weight: 400;
  font-size: 24px;
  line-height: 150%;
  display: flex;
  align-items: center;
  text-align: center;
  color: #2CC3F3;
  justify-content: center;
  padding-left: 20px;
  padding-right: 20px;
  padding-top: 10px;
  padding-bottom: 10px;
}
</style>
