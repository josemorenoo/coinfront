<script setup>
import SearchBar from '../components/topten/SearchBar.vue';
import TimeFrameSelector from '../components/topten/TimeFrameSelector.vue';
</script>

<template>
  <div class="topten">
    <div class="title">Top 10</div>
    <div class="input-row">
      <SearchBar />
      <TimeFrameSelector />
    </div>
  </div>
</template>


<style>
@media (min-width: 1024px) {
  .topten {
    display: flex;
    flex-direction: column;
    padding-top: 72px;
    overflow-y: auto;
    height: 100%;
    padding-left: 7rem;
  }

  .title {
    width: 75%;

    /* Desktop Header 4 */

    font-family: 'Roboto';
    font-style: normal;
    font-weight: 400;
    font-size: 24px;
    line-height: 150%;
    /* or 36px */

    text-align: left;

    /* F6F8FF */

    color: #F6F8FF;
    margin-top: 4rem;
  }

  .input-row {
    justify-content: left;
    padding-top: 1rem;
    display: flex;
    flex-direction: row;
    gap: 2rem;
  }
}
</style>