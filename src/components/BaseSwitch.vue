<script>
import { Switch } from "@headlessui/vue";
import { ref } from "vue";

export default {
  name: "BaseSwitch",
  components: { Switch },
  setup() {
    const enabled = ref(false);

    return { enabled };
  },
};
</script>

<template>
  <Switch
    v-model="enabled"
    :class="enabled ? 'bg-yellow-900' : 'bg-yellow-700'"
    class="
      relative
      inline-flex
      flex-shrink-0
      h-[38px]
      w-[74px]
      border-2 border-transparent
      rounded-full
      cursor-pointer
      transition-colors
      ease-in-out
      duration-200
      focus:outline-none
      focus-visible:ring-2
      focus-visible:ring-white
      focus-visible:ring-opacity-75
    "
  >
    <span class="sr-only">Use setting</span>
    <span
      aria-hidden="true"
      :class="enabled ? 'translate-x-9' : 'translate-x-0'"
      class="
        pointer-events-none
        inline-block
        h-[34px]
        w-[34px]
        rounded-full
        bg-white
        shadow-lg
        ring-0
        transition
        ease-in-out
        duration-200
      "
    />
  </Switch>
</template>
