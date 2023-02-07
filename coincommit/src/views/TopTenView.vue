<template>
  <div class="topten">
    <h1>Top 10 page</h1>
  </div>
</template>

.topten { 
  flex-grow: 100;
}

<style>
@media (min-width: 1024px) {
  .topten {
    min-height: 100vh;
    display: flex;
    align-items: center;
    flex-grow: 100;
  }
}
</style>