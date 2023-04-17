<template>
  <main>
    <div class="container grid">
      <SideBar />
      <SearchBar />
      <CertificatesList />
      <FiltersSection />
      <ActionsSection />
    </div>
    <StatusBar />
  </main>
</template>

<script>
import StatusBar from '@/components/StatusBar.vue'
import SideBar from '@/components/SideBar.vue'
import SearchBar from '@/components/SearchBar.vue'
import CertificatesList from '~/components/CertificatesList.vue'
import FiltersSection from '@/components/FiltersSection.vue'
import ActionsSection from '@/components/ActionsSection.vue'
export default {
  comments: {
    StatusBar,
    SideBar,
    SearchBar,
    CertificatesList,
    FiltersSection,
    ActionsSection,
  },
}
</script>

<style scoped>
.container {
  width: 100%;
  background: #2e3138;
  grid-template-columns: 183px 4fr 2fr;
  grid-template-rows: 60px 0.8fr 1fr;
}
</style>