<script>
import { defineProps } from 'vue';
export default {
  props: defineProps({
    label: {
      type: String,
      default: '',
    },
    modelValue: {
      type: [String, Number],
      default: '',
    },
  }),
};
</script>
<template>
  <label v-if="label">{{ label }}</label>
  <input :placeholder="label" class="field" :value="modelValue" />
</template>
