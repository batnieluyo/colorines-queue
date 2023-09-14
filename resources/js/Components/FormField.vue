<script>
const props = defineProps([
    'label',
    'input_type'
])
</script>

<template>
  <div class="grid grid-cols-1 space-y-1">
    <label for="">{{ props.label }}</label>
    <input :type="props.input_type" class="border rounded">
  </div>
</template>