<template lang="pug">
  span.MenuUi.menu
    template(v-for='group in groups', )

      .menu-label.
        {{ group.label }}

      template(v-if='group.items')
        ul.menu-list
          template(v-for='item in group.items', )
            li
              template(v-if='item.link.type === "router"')
                router-link(:to='{name: item.link.name}')
                  template(v-if='item.icon')
                    icon-ui(:type='item.icon')
                  span.
                    {{ item.text }}
              template(v-else)
                a(@click='clickItem(item)')
                  template(v-if='item.icon')
                    icon-ui(:type='item.icon')
                  span.
                    {{ item.text }}
              template(v-if='item.subitems')
                ul
                  template(v-for='subitem in item.subitems', )
                    li
                      router-link(:to='{name: subitem.link.name}')
                        template(v-if='subitem.icon')
                          icon-ui(:type='subitem.icon')
                        span.
                          {{ subitem.text }}
</template>

<script>
import IconUi from '@/components/ui/elements/IconUi/IconUi'

export default {
  name: 'MenuUi',
  components: {
    IconUi,
  },
  props: {
    groups: {
      default: () => [],
      type: Array,
      required: true,
    },
  },
  methods: {
    clickItem (item) {
      this.$emit('click', item)
    },
  },
}
</script>

<style lang="stylus">
.MenuUi
  .icon
    opacity .7
    margin-right 5px
</style>
