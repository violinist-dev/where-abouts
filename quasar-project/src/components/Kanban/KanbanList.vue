<template>
  <div class="rounded-borders" >
    <q-toolbar :class="props.headerCss">
      <q-toolbar-title>{{ props.title }}</q-toolbar-title>
    </q-toolbar>
    <q-list bordered  :class="props.bodyCss">
      <draggable
        class="list-group"
        :list="props.list"
        group="people"
        @change="log"
        itemKey="id"
      >
        <template #item="{ element }">
          <q-item class="q-my-sm" clickable v-ripple>
            <q-item-section avatar>
              <q-avatar v-if="!element.avatar" color="primary" text-color="white">
                {{ element.letter }}
              </q-avatar>
              <q-avatar v-if="element.avatar">
                <img :src="`https://cdn.quasar.dev/img/${element.avatar}`">
              </q-avatar>
            </q-item-section>

            <q-item-section>
              <q-item-label>{{ element.name }}</q-item-label>
              <q-item-label caption lines="1">{{ element.email }}</q-item-label>
            </q-item-section>

            <q-item-section side>
              <q-icon name="chat_bubble" color="green" />
            </q-item-section>
            </q-item>
        </template>
      </draggable>
    </q-list>
  </div>
</template>

<script setup>
import draggable from 'vuedraggable'

const props = defineProps(['title', 'headerCss', 'bodyCss', 'list'])

function log(evt) {
  // window.console.log(evt)
}
</script>

<style scoped lang="scss">
.list-group {
  min-height: 25px
}
</style>

