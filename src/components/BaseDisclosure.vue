<template>
  <Disclosure v-slot="{ open, close }" defaultOpen>
    <DisclosureButton class="text-[#2f54f7] text-[1.5rem]">
      Is team pricing available? {{ open }}
      <button @click="close">Close</button>
    </DisclosureButton>
    <DisclosurePanel v-slot="{ close }">
      Yes! You can purchase a license that you can share with your entire team.
      <DisclosureButton>Home</DisclosureButton>
      <button @click="close">Close</button>
    </DisclosurePanel>
  </Disclosure>
</template>

<script>
import { Disclosure, DisclosureButton, DisclosurePanel } from "@headlessui/vue";

export default {
  components: { Disclosure, DisclosureButton, DisclosurePanel },
};
</script>
