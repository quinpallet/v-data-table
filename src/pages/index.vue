<script setup lang="ts">
const headers = ref(headerList);
const items = ref(itemList);
// ヘッダーの各項目にwidthと同値のminWidthとmaxWidthを設定
headers.value = headers.value.map((o) => ({
  ...o,
  minWidth: o.width,
  maxWidth: o.width,
}));
</script>

<template>
  <!-- <v-btn text="connect" @click="() => ble_connect()"></v-btn> -->
  <v-data-table
    :headers="headers"
    :items="items"
    color="indigo"
    theme="indigo"
    items-per-page="100"
    height="100vh"
    density="compact"
    fixed-header
    sticky
    hide-default-footer
  ></v-data-table>
</template>

<style scoped lang="scss">
.v-data-table {
  :deep(table) {
    thead {
      th {
        color: rgb(var(--v-theme-surface)) !important;
        background: rgb(var(--v-theme-info)) !important;
      }
    }
  }
}
</style>
