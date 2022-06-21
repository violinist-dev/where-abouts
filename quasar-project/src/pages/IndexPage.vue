<template>
  <q-page class="q-pa-md">
    <div class="q-pb-md text-caption">Update staff where abouts by dragging their names to the appropriate area.</div>

    <div class="board row q-col-gutter-md">
      <!-- in the office -->
      <div :class="spacingCss">
        <kanban-list
          title="In the Office"
          header-css="bg-green text-white"
          body-css="bg-green-1"
          :list="inTheOffice"
          />
      </div>
      <!-- working remotely -->
      <div :class="spacingCss">
        <kanban-list
          title="Working Remotely"
          header-css="bg-blue text-white"
          body-css="bg-blue-1"
          :list="workingRemotely"
          />
      </div>
      <!-- Out of office -->
      <div :class="spacingCss">
        <kanban-list
          title="Out of Office"
          header-css="bg-blue-grey-5 text-white"
          body-css="bg-blue-grey-1"
          :list="outOfOffice"
          />
      </div>
      <!-- On Leave -->
      <div :class="spacingCss">
        <kanban-list
          title="On Leave"
          header-css="bg-grey text-white"
          body-css="bg-grey-1"
          :list="onLeave"
          />
      </div>
    </div>

  </q-page>
</template>

<script setup>
import { ref } from 'vue'
import { useStoreStaff } from 'stores/storeStaff'
import KanbanList from 'components/Kanban/KanbanList.vue'

const store = useStoreStaff()

const spacingCss = "col-xs-12 col-sm-6 col-lg-3"

const inTheOffice = ref(store.getStaffInTheOffice)
const workingRemotely = ref(store.getStaffWorkingRemotely)
const outOfOffice = ref(store.getStaffOutOfOffice)
const onLeave = ref(store.getStaffOnLeave)

</script>

