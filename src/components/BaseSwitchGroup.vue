<template>
  <SwitchGroup>
    <SwitchLabel :passive="false" class="cursor-pointer select-none mr-4"
      >Enable notifications</SwitchLabel
    >
    <Switch v-model="enabled" v-slot="{ checked }"
      >{{ enabled }}{{ checked }}</Switch
    >
    <SwitchDescription>This is a switch</SwitchDescription>
  </SwitchGroup>
</template>

<script>
import { ref } from "vue";
import { Switch, SwitchGroup, SwitchLabel, SwitchDescription } from "@headlessui/vue";

export default {
  components: { Switch, SwitchGroup, SwitchLabel, SwitchDescription },

  setup() {
    const enabled = ref(false);

    return { enabled };
  },
};
</script>
