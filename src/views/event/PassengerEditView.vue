<script setup lang="ts">
import { ref, toRefs } from 'vue';
import { useRouter } from 'vue-router';
import { type Event } from '@/types';
import { useMessageStore } from '@/stores/message';

const props = defineProps<{ 
  event: Event
  id: String
}>()
// eslint-disable-next-line @typescript-eslint/no-unused-vars
const { event } = toRefs(props);
const router = useRouter();
const store = useMessageStore()

const editEvent = () => { 
  store.updateMessage('the update is in progress ')
  setTimeout(() => {
    store.resetMessage()
  }, 5000)
  router.push({ name: 'passenger-list-view'})
};
</script>
<template>
    <div>
    <p>Edit passenger here</p>
    <button @click="editEvent">Edit</button>
  </div>
</template>