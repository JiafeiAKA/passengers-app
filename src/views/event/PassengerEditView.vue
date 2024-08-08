<script setup lang="ts">
import { ref, toRefs } from 'vue';
import { useRouter } from 'vue-router';
import { type Event } from '@/types';

const props = defineProps<{ 
  event: Event
  id: String
}>()
// eslint-disable-next-line @typescript-eslint/no-unused-vars
const { event } = toRefs(props);
const router = useRouter();

const editEvent = () => { 
  router.push({ name: 'passenger-detail'});
};
</script>
<template>
    <div>
    <p>Edit passenger here</p>
    <button @click="editEvent">Edit</button>
  </div>
</template>