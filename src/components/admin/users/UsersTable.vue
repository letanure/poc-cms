<template lang="pug">
  .UsersAdmin

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
  name: 'UsersAdmin',
  components: {
    AdminTable,
  },
  data () {
    return {
      itemKey: 'id',
      itemPlural: 'Users',
      itemSingular: 'User',
      routeAddName: 'UsersAdd',
      routeEditName: 'UsersEdit',
      storeGetter: 'usersList',
      storeRemove: 'userRemove',
      tableCols: [
        { label: 'Name', prop: 'name' },
        { label: 'Email', prop: 'email' },
      ],
    }
  },
}
</script>

<style lang="stylus">
// .UsersAdmin
</style>
