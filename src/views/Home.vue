<template>
  <div class="container">
    <div class="row">
      <div class="col">
        <search-bar></search-bar>
      </div>
    </div>
    <div class="row">
      <div
        class="col-12 col-sm-6 col-md-4 col-lg-2 p-2"
        v-for="computer in total"
        :key="computer.id"
      >
        <AssetCard :computer="computer"></AssetCard>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import AssetCard from '@/components/AssetCard.vue';
import SearchBar from '@/components/SearchBar.vue';
export default {
  components: { AssetCard, SearchBar },
  name: "Test",
  created() { console.log('created') },
  data() {
    return {
      total: [{ id: 1, name: 'computer', type: 'Desktop' }, { id: 1, name: '123', type: 'Printer' }, { id: 2, name: 'computer', type: 'Server' }, { id: 3, name: 'computer', type: 'VoipPhone' }, { id: 4, name: 'smartphone', type: 'Smartphone' },]
    };
  },
  props: {},
  methods: {},
};
</script>

<style lang="scss" scoped>
</style>