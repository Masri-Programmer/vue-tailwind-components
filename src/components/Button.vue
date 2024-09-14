<template>
  <button
    :class="computedClasses"
    :disabled="loading || disabled"
    @click="handleClick"
  >
    <span v-if="loading" class="loader"></span>
    <span v-else>{{ label }}</span>
  </button>
</template>

<script setup lang="ts">
import { defineProps, computed, defineEmits } from "vue";

const props = defineProps({
  label: {
    type: String,
    default: "Button",
  },
  type: {
    type: String as () => "button" | "submit" | "reset",
    default: "button",
  },
  variant: {
    type: String as () => "primary" | "secondary" | "danger" | "success",
    default: "primary",
  },
  size: {
    type: String as () => "sm" | "md" | "lg",
    default: "md",
  },
  block: {
    type: Boolean,
    default: false,
  },
  loading: {
    type: Boolean,
    default: false,
  },
  disabled: {
    type: Boolean,
    default: false,
  },
});

const emit = defineEmits(["click"]);

const handleClick = (e: Event) => {
  if (!props.loading && !props.disabled) {
    emit("click", e);
  }
};

const computedClasses = computed(() => {
  const baseClasses =
    "font-semibold rounded focus:outline-none focus:ring-2 focus:ring-offset-2";
  const variantClasses = {
    primary: "bg-blue-500 hover:bg-blue-600 text-white focus:ring-blue-500",
    secondary: "bg-gray-500 hover:bg-gray-600 text-white focus:ring-gray-500",
    danger: "bg-red-500 hover:bg-red-600 text-white focus:ring-red-500",
    success: "bg-green-500 hover:bg-green-600 text-white focus:ring-green-500",
  }[props.variant];

  const sizeClasses = {
    sm: "px-3 py-1.5 text-sm",
    md: "px-4 py-2 text-base",
    lg: "px-6 py-3 text-lg",
  }[props.size];

  const blockClass = props.block ? "w-full" : "";

  const disabledClass = props.disabled ? "opacity-50 cursor-not-allowed" : "";

  return `${baseClasses} ${variantClasses} ${sizeClasses} ${blockClass} ${disabledClass}`;
});
</script>

<style scoped>
.loader {
  border: 2px solid transparent;
  border-top-color: white;
  border-radius: 50%;
  width: 1rem;
  height: 1rem;
  animation: spin 1s linear infinite;
}

@keyframes spin {
  to {
    transform: rotate(360deg);
  }
}
</style>
