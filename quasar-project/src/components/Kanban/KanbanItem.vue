<template>
  <q-item @click="click" class="q-my-sm" clickable v-ripple>
    <q-item-section avatar>
      <q-avatar v-if="!element.avatar" :color="avatarColor" text-color="white">
        <img :src="`https://api.dicebear.com/6.x/avataaars/svg?seed=${element.name}`" />
      </q-avatar>
      <q-avatar v-if="element.avatar">
        <img :src="`http://localhost:8000${element.avatar}`" />
      </q-avatar>
    </q-item-section>

    <q-item-section>
      <q-item-label>{{ element.name }}</q-item-label>
    </q-item-section>
  </q-item>
</template>

<script setup>
import { computed } from 'vue'
import { useStoreAuthentication } from 'stores/storeAuthentication'

// props and emits
const props = defineProps({
  element: {
    type: Object,
  },
})
const emit = defineEmits(['click'])

const authStore = useStoreAuthentication()

const avatarColor = computed(() => {
  if (canUpdate(props.element.addedBy)) {
    return "accent"
  }
  else {
    return "primary"
  }
})

function canUpdate(addedBy) {
  return authStore.permissions.canEditAll ||
    authStore.permissions.canEditOwn && Number(authStore.uid) === addedBy
}

function click() {
  emit('click')
}
</script>
