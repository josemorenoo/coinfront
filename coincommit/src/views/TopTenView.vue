<script setup>
import SearchBar from '../components/topten/SearchBar.vue';
import TimeFrameSelector from '../components/topten/TimeFrameSelector.vue';
import SortableTable from '../components/topten/SortableTable.vue';
import Footer from "../components/Footer.vue";
</script>

<template>
  <div class="topten">
    <div class="topten-container">
      <div class="title">Top 10</div>
      <div class="input-row">
        <SearchBar />
        <TimeFrameSelector />
      </div>
      <SortableTable :columns="this.columns" :tableData="this.tableData" />
    </div>
    <Footer />
  </div>
</template>



<script>
export default {
  name: "TopTenView",
  components: {
    SortableTable
  },
  data() {
    return {
      columns: [
        { label: "Project", key: "project" },
        { label: "Price Change", key: "price_change" },
        { label: "Consecutive Days", key: "consecutive_days" },
        { label: "Authors", key: "authors" },
        { label: "Lines of Code", key: "lines_of_code" },
      ],
      tableData: [
        { project: "BTC", price_change: "2,000 (+18%)", consecutive_days: "432", authors: "22", lines_of_code: 847 },
        { project: "ETH", price_change: "5,000 (1%)", consecutive_days: "23", authors: "53", lines_of_code: 4534 },
        { project: "ACH", price_change: "8,000 (+14%)", consecutive_days: "43", authors: "23", lines_of_code: 765 },
        { project: "ALGO", price_change: "-3,000 (-18%)", consecutive_days: "3", authors: "7", lines_of_code: 4354 },
        { project: "RAD", price_change: "1,000 (+14%)", consecutive_days: "6346", authors: "4", lines_of_code: 734 },
        { project: "DOGE", price_change: "4,000 (+12%)", consecutive_days: "34", authors: "5", lines_of_code: 5678 },
        { project: "EOS", price_change: "7,000 (+17%)", consecutive_days: "87", authors: "8", lines_of_code: 56 },
        { project: "FEI", price_change: "6,000 (+4%)", consecutive_days: "12", authors: "3", lines_of_code: 345 },
        { project: "CARD", price_change: "1,000 (+10%)", consecutive_days: "1", authors: "3", lines_of_code: 8647 },
        { project: "POLY", price_change: "1,000 (+11%)", consecutive_days: "0", authors: "23", lines_of_code: 3456 },
      ],
    }
  }
}
</script>

<style>
.topten {
  display: flex;
  flex-direction: column;
  overflow-y: scroll;
  height: 100%;
  justify-content: space-between;
}

.topten-container {
  padding-top: 4rem;
  padding-left: 7rem;
  height: 100%;
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
</style>