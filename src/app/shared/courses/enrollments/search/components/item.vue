<script>
import resources from '@/crud/search/components/item'

export default {
  name: 'enrollments-index-item',
  mixins: [resources]
}
</script>

<template lang="pug">
tr
  td
    strong {{ item | getValue('group.complete_label') }}
  td {{ item | getValue('student.name') }}
  td {{ item | getValue('route.label') }}
  td(v-if="buttonSelect")
    button.btn.btn-primary.pull-right(@click.prevent="doSelect(item)") Selecionar
  td(v-if="!noActions")
    slot
    a.btn.btn-circle-micro.btn-danger(@click.prevent="doDelete(item)")
      span.fa.fa-close
</template>
