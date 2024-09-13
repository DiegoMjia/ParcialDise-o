<template>
  <div class="home">
    <HeaderWeb></HeaderWeb>
    <MainContent></MainContent>
    <FlexAxios></FlexAxios>
  </div>
</template>

<script>
import HeaderWeb from '@/components/HeaderWeb.vue';
import MainContent from '@/components/MainContent.vue';
import FlexAxios from '@/components/FlexAxios.vue';

export default {
  name: 'HomeView',
  components: {
    HeaderWeb,
    MainContent,
    FlexAxios
  }
}
</script>
