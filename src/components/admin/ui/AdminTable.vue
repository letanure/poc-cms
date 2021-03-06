<template lang="pug">
  .AdminTable

    template(v-if='hasList')
      table.table.is-striped.is-hoverable.is-fullwidth()
        thead
          tr
            template(v-for='(col, index) in tableCols')
              th.
                {{ col.label }}
            th.
              Actions
        tbody(is='transition-group', name='tableRowSlide')
          tr(v-for='(itemRow, key) in storeList', :key='key')
            template(v-for='(col, index) in tableCols')
              td.
                {{ itemRow[col.prop] }}
            td
              button-ui(
                color='info',
                iconType='pencil',
                :outlined='true',
                size='small',
                tag='router-link',
                text='Edit',
                :to='{ name: routeEditName, params: { slug: itemRow[itemKey] }}',
                )
              button-ui(
                @click='confirmRemove(key)',
                color='danger',
                iconType='trash',
                :outlined='true',
                size='small',
                tag='button',
                text='Delete',
                )

              template(v-for='action in extraActions')
                button-ui(v-bind='actionWithSlug(itemRow[itemKey], action)')

    template(v-else)
      h5.title.is-5
        span.
          No {{ itemPlural }} yet.
      router-link.button.is-info(:to='{ name: routeAddName }', ).
        Add your first {{ itemSingular }}

    transition(name='fade', appear)
      confirm-ui(v-show='activeModal'
        @close='checkAnswer($event)',
        :active='activeModal',
        :answer-no='confirmAnswerNo',
        :answer-yes='confirmAnswerYes',
        :message='confirmMessage',
        :title='confirmTitle',
      )
</template>

<script>
import { ButtonUi, ConfirmUi, IconUi } from '@/components/ui'

export default {
  name: 'AdminTable',
  components: {
    ButtonUi,
    ConfirmUi,
    IconUi,
  },
  props: {
    extraActions: {
      default: () => [],
      type: Array,
      required: false,
    },
    itemKey: {
      default: '',
      type: String,
      required: false,
    },
    itemPlural: {
      default: 'Items',
      type: String,
      required: false,
    },
    itemSingular: {
      default: 'Item',
      type: String,
      required: false,
    },
    routeAddName: {
      default: '',
      type: String,
      required: true,
    },
    routeEditName: {
      default: '',
      type: String,
      required: true,
    },
    storeGetter: {
      default: '',
      type: String,
      required: true,
    },
    storeRemove: {
      default: '',
      type: String,
      required: true,
    },
    tableCols: {
      default: () => [],
      type: Array,
      required: true,
    },
  },
  data () {
    return {
      activeModal: false,
      collection: [],
      collectionRef: null,
      collectionTableItem: [],
      deletingItemKey: null,
      labelPlural: 'Collections',
      labelSingular: 'Item',
      routeNameAdd: 'home',
    }
  },
  computed: {
    confirmAnswerNo () {
      return `No, keep the ${this.labelSingular}`
    },

    confirmAnswerYes () {
      return `Yes, delete ${this.labelSingular}`
    },

    confirmMessage () {
      return `Deleting a ${this.labelSingular} will remove it from your list.`
    },

    confirmTitle () {
      return `Delete ${this.labelSingular}?`
    },

    hasList () {
      return Object.keys(this.storeList).length > 0
    },

    storeList () {
      return this.$store.getters[this.storeGetter]
    },
  },
  mounted () {
    this.labelSingular = this.itemSingular
    this.labelPlural = this.itemPlural
  },
  methods: {
    actionWithSlug (itemKey, action) {
      action.to.params = {
        slug: itemKey,
      }
      return action
    },

    checkAnswer (answer) {
      this.activeModal = false
      if (answer) {
        this.remove(this.deletingItemKey)
      }
      this.deletingItemKey = null
    },

    confirmRemove (key) {
      this.deletingItemKey = key
      this.activeModal = true
    },

    remove (key) {
      this.$store.dispatch(this.storeRemove, key)
    },
  },
}
</script>

<style lang="stylus">
.AdminTable
  .button
    margin-right 5px

    &:last-children
      margin-right 0

  .tableRowSlide-enter-active, .tableRowSlide-leave-active
    transition all .3s linear
  .tableRowSlide-enter, .tableRowSlide-leave-to
    opacity 0
    transform translateX(50px)

  .fade-enter-active, .fade-leave-active
    transition opacity .3s linear
  .fade-enter, .fade-leave-to
    opacity 0
</style>
