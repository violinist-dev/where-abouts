<template>
  <q-page class="q-pa-md">
    <div class="q-pb-md text-caption">Update staff where abouts by dragging their names to the appropriate area.</div>

    <div class="board row q-gutter-md">
      <!-- in the office -->
      <div class="col">
        <q-toolbar class="bg-green text-white">
          <q-toolbar-title>In the Office</q-toolbar-title>
        </q-toolbar>
        <q-list bordered class="bg-green-1">

          <q-item v-for="contact in inTheOffice" :key="contact.id" class="q-my-sm" clickable v-ripple>
            <q-item-section avatar>
              <q-avatar color="primary" text-color="white">
                {{ contact.letter }}
              </q-avatar>
            </q-item-section>

            <q-item-section>
              <q-item-label>{{ contact.name }}</q-item-label>
              <q-item-label caption lines="1">{{ contact.email }}</q-item-label>
            </q-item-section>

            <q-item-section side>
              <q-icon name="chat_bubble" color="green" />
            </q-item-section>
          </q-item>
        </q-list>
      </div>
      <!-- working remotely -->
      <div class="col">
        <q-toolbar class="bg-blue text-white">
          <q-toolbar-title>Working Remotely</q-toolbar-title>
        </q-toolbar>
        <q-list bordered class="bg-blue-1">
          <q-item v-for="contact in workingRemotely" :key="contact.id" class="q-mb-sm" clickable v-ripple>
            <q-item-section avatar>
              <q-avatar>
                <img :src="`https://cdn.quasar.dev/img/${contact.avatar}`">
              </q-avatar>
            </q-item-section>

            <q-item-section>
              <q-item-label>{{ contact.name }}</q-item-label>
              <q-item-label caption lines="1">{{ contact.email }}</q-item-label>
            </q-item-section>

            <q-item-section side>
              <q-icon name="chat_bubble" color="grey" />
            </q-item-section>
          </q-item>
        </q-list>
      </div>
      <!-- Out of office -->
      <div class="col">
        <q-toolbar class="bg-red-5 text-white">
          <q-toolbar-title>Out of Office</q-toolbar-title>
        </q-toolbar>
        <q-list bordered class="bg-red-1">
          <q-item v-for="contact in outOfOffice" :key="contact.id" class="q-mb-sm" clickable v-ripple>
            <q-item-section avatar>
              <q-avatar>
                <img :src="`https://cdn.quasar.dev/img/${contact.avatar}`">
              </q-avatar>
            </q-item-section>

            <q-item-section>
              <q-item-label>{{ contact.name }}</q-item-label>
              <q-item-label caption lines="1">{{ contact.email }}</q-item-label>
            </q-item-section>

            <q-item-section side>
              <q-icon name="chat_bubble" color="grey" />
            </q-item-section>
          </q-item>
        </q-list>
      </div>


    </div>
  </q-page>
</template>

<script setup>

const inTheOffice = [ {
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
} ]

const workingRemotely = [ {
  id: 5,
  name: 'Brunhilde Panswick',
  email: 'bpanswick4@csmonitor.com',
  avatar: 'avatar2.jpg'
}, {
  id: 6,
  name: 'Winfield Stapforth',
  email: 'wstapforth5@pcworld.com',
  avatar: 'avatar6.jpg'
} ]

const outOfOffice = [ {
  id: 7,
  name: 'Ainsof So\'o',
  email: 'ainsofs@csmonitor.com',
  avatar: 'avatar4.jpg'
}, {
  id: 8,
  name: 'Billy Chan-Ting',
  email: 'billyc@pcworld.com',
  avatar: 'avatar1.jpg'
} ]


</script>
