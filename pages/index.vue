<template> 
  <div v-for="currency in data.data" :key="currency">
    <ul class="ticker">
      <li class="property">A currency:</li>
      <li class="property">{{ currency.name}}</li>
      <li class="property">{{ currency.symbol }}</li>
      <li class="property">{{ currency.price_usd }}</li>
      <li class="property">
        <NuxtLink :to="'currency/'+ currency.id">{{ currency.id }}</NuxtLink>
      </li>
    </ul>
  </div>
</template>

<script setup>
  const {data} = await useFetch('/api/tickers?limit=10')
</script>

<style scoped>
.ticker {
  display: inline;
}
.property{
    display: inline;
  }
</style>