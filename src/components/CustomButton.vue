<script setup lang="ts">
const props = defineProps({
  href: String,
  to: String,
  disabled: { type: Boolean, default: false },
  blockMode: { type: Boolean, default: false }
})
defineEmits<{
  (e: 'smash', payload: MouseEvent): void
}>()

const linkClicked = () => {
  if (!props.disabled && props.href) window.location.href = props.href
}
</script>

<template>
  <a
    v-if="href"
    :href="href"
    :class="{ 'btn-disabled': disabled, 'display-block': blockMode }"
    class="btn"
    @click.prevent="linkClicked"
  >
    <slot></slot>
  </a>
  <router-link
    v-else-if="to"
    :to="!disabled ? to : ''"
    :class="{ 'btn-disabled': disabled, 'display-block': blockMode }"
    class="btn"
    :disabled="disabled"
  >
    <slot></slot>
  </router-link>
  <button
    v-else
    :class="{ 'btn-disabled': disabled, 'display-block': blockMode }"
    class="btn"
    :disabled="disabled"
    @click="$emit('smash', $event)"
  >
    <slot></slot>
  </button>
</template>

<style scoped>
.btn {
  padding: 14px 24px;
  border-radius: 24px;
  border-style: solid;
  text-decoration: none;
  cursor: pointer;
  font: inherit;
  display: inline-flex;
  flex-direction: column;
  align-items: center;
}

.display-block {
  display: block;
}

.btn:hover {
  opacity: 0.4;
}

.btn-disabled {
  opacity: 0.4;
  cursor: default;
}

.btn:focus:not(.btn-disabled) {
  font-weight: bold;
}

.btn-primary {
  background-color: var(--primary);
  border-color: var(--primary);
  color: white;
}

.btn-primary.btn-outline {
  color: var(--primary);
}

.btn-primary.btn-outline:hover {
  color: var(--primary);
}

.btn-secondary {
  background-color: var(--secondary);
  border-color: var(--secondary);
  color: white;
}

.btn-secondary.btn-outline {
  color: var(--secondary);
}

.btn-danger {
  background-color: var(--danger);
  border-color: var(--danger);
  color: white;
}

.btn-danger.btn-outline {
  color: var(--danger);
}

.btn-warning {
  background-color: var(--warning);
  border-color: var(--warning);
  color: black;
}

.btn-warning.btn-outline {
  color: var(--warning);
}

.btn-success {
  background-color: var(--success);
  border-color: var(--success);
  color: white;
}

.btn-success.btn-outline {
  color: var(--success);
}

.btn-small {
  padding: 10px 16px;
}

.btn-large {
  padding: 16px 24px;
}

.btn-outline {
  background-color: transparent;
}
</style>
