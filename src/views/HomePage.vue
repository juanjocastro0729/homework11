<script setup>
import MainCards from '@/components/MainCards.vue';
import MainPagination from '@/components/MainPagination.vue';

import { onMounted } from 'vue'
import useAPI from '@/composables/useAPI';
//const title = ref('Hello There ✋')

const { getEmployees, loading } = useAPI()

onMounted(async () => {
    await getEmployees()
})

</script>

<template>
  <p v-if="loading">LOADING...</p>
  <div v-else>
    <MainCards></MainCards>
    <MainPagination></MainPagination>
  </div>
  
</template>
