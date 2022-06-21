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
import KanbanList from 'components/Kanban/KanbanList.vue'

const spacingCss = "col-xs-12 col-sm-6 col-lg-3"

const inTheOffice = ref([ {
  id: 1,
  name: 'Ruddy Jedrzej',
  email: 'rjedrzej0@discuz.net',
  letter: 'R'
}, {
  id: 2,
  name: 'Mallorie Alessandrini',
  email: 'malessandrini1@marketwatch.com',
  letter: 'M'
}, {
  id: 3,
  name: 'Elisabetta Wicklen',
  email: 'ewicklen2@microsoft.com',
  letter: 'E'
}, {
  id: 4,
  name: 'Seka Fawdrey',
  email: 'sfawdrey3@wired.com',
  letter: 'S'
} ])

const workingRemotely = ref([ {
  id: 5,
  name: 'Brunhilde Panswick',
  email: 'bpanswick4@csmonitor.com',
  avatar: 'avatar2.jpg'
}, {
  id: 6,
  name: 'Winfield Stapforth',
  email: 'wstapforth5@pcworld.com',
  avatar: 'avatar6.jpg'
} ])

const outOfOffice = ref([ {
  id: 7,
  name: 'Ainsof So\'o',
  email: 'ainsofs@csmonitor.com',
  avatar: 'avatar4.jpg'
}, {
  id: 8,
  name: 'Billy Chan-Ting',
  email: 'billyc@pcworld.com',
  avatar: 'avatar1.jpg'
} ])

const onLeave = ref([])

</script>

