<template lang="pug">
  .AssetsAdmin

    admin-table(
      :itemKey='itemKey',
      :itemPlural='itemPlural',
      :itemSingular='itemSingular',
      :routeAddName='routeAddName',
      :routeEditName='routeEditName',
      :storeGetter='storeGetter',
      :storeRemove='storeRemove',
      :tableCols='tableCols',
      )
</template>

<script>
import { AdminTable } from '@/components/admin/ui'

export default {
  name: 'AssetsAdmin',
  components: {
    AdminTable,
  },
  data () {
    return {
      itemKey: 'id',
      itemPlural: 'Assets',
      itemSingular: 'Asset',
      routeAddName: 'AssetsAdd',
      routeEditName: 'AssetsEdit',
      storeGetter: 'assetsList',
      storeRemove: 'assetRemove',
      subtitle: 'Assets description',
      tableCols: [
        { label: 'Name', prop: 'name' },
        { label: 'Type', prop: 'type' },
      ],
    }
  },
}
</script>

<style lang="stylus">
// .AssetsAdmin
</style>
