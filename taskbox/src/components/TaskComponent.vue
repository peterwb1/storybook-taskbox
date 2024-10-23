<template>
    <div class="list-item">
      <label for="title" :aria-label="task.title">
        <input type="text" readonly :value="task.title" id="title" name="title" />
      </label>
    </div>
  </template>
  
<script setup lang="ts">
  defineProps({
    task: {
      type: Object,
      required: true,
      default: () => ({ id: '', state: '', title: '' }),
      validator: (task) => ['id', 'state', 'title'].every((key) => key in task)
    }
  });
</script>