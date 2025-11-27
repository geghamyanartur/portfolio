<template>
  <Teleport to="body">
    <div
      v-if="modelValue"
      class="fixed inset-0 z-50 flex items-center justify-center px-4 py-6"
    >
      <div
        class="absolute inset-0 bg-black/70 backdrop-blur-sm"
        @click="close"
      />

      <div
        class="relative w-full max-w-5xl overflow-hidden rounded-2xl border border-slate-800/80 bg-slate-950/90 shadow-2xl shadow-slate-900/70"
      >
        <header class="flex items-center justify-between gap-3 border-b border-slate-800/70 px-6 py-4">
          <div class="space-y-1">
            <h3 class="text-lg font-semibold text-slate-50">{{ title }}</h3>
          </div>
          <button
            type="button"
            class="inline-flex h-9 w-9 items-center justify-center rounded-full border border-slate-700/70 text-slate-300 hover:border-brand-400 hover:text-brand-200 transition-colors"
            @click="close"
            aria-label="Close dialog"
          >
            <span class="text-xl leading-none">×</span>
          </button>
        </header>

        <div class="max-h-[80vh] overflow-auto bg-gradient-to-b from-slate-950/80 to-slate-950 px-4 pb-4 pt-2 sm:px-6">
          <slot />
        </div>
      </div>
    </div>
  </Teleport>
</template>

<script setup>
const props = defineProps({
  modelValue: {
    type: Boolean,
    default: false,
  },
  title: {
    type: String,
    default: '',
  },
})

const emit = defineEmits(['update:modelValue'])

const close = () => {
  emit('update:modelValue', false)
}
</script>
