<template>
  <section class="home-page">
    <h1 class="page-title">홈</h1>

    <SummaryCards :income="summary.income" :expense="summary.expense" :balance="summary.balance" />

    <div class="home-grid">
      <ExpensePieChart :items="categoryExpenseList" />
    </div>
  </section>
</template>

<script setup>
import { computed, onMounted } from 'vue';
import { useLedgerStore } from '@/stores/ledger';
import SummaryCards from '@/components/home/SummaryCards.vue';
import ExpensePieChart from '@/components/home/ExpensePieChart.vue';

const ledgerStore = useLedgerStore();

onMounted(() => {
  ledgerStore.fetchTransactions();
  ledgerStore.fetchCategories();
});

const summary = computed(() => ledgerStore.monthSummary);
const categoryExpenseList = computed(() => ledgerStore.categoryExpenseList);
</script>

<style scoped>
.page-title {
  margin-bottom: 20px;
  font-size: 28px;
  font-weight: 700;
}

.home-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 20px;
}
</style>
