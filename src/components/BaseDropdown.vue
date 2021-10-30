<template>
  <Menu as="div" v-slot="{ open }">
    {{ open }}
    <MenuButton v-slot="{ open }">
      Options {{ open }}
      <ChevronDownIcon aria-hidden="true" />
    </MenuButton>

    <transition
      enter-active-class="transition duration-100 ease-out"
      enter-from-class="transform scale-95 opacity-0"
      enter-to-class="transform scale-100 opacity-100"
      leave-active-class="transition duration-75 ease-out"
      leave-from-class="transform scale-100 opacity-100"
      leave-to-class="transform scale-95 opacity-0"
    >
      <MenuItems :static="false" :unmount="false" v-slot="{ open }">
        {{ open }}
        <div v-for="(menuGroup, i) in menu" :key="i">
          <MenuItem
            v-for="(item, j) in menuGroup"
            :key="`${i}-${j}`"
            v-slot="{ active, disabled }"
            class="block"
            :disabled="item.disabled"
          >
            <button>{{ item.label }} | active: {{ active }} | disabled: {{ disabled }}</button>
          </MenuItem>
        </div>
      </MenuItems>
    </transition>
  </Menu>
</template>

<script>
import { Menu, MenuButton, MenuItems, MenuItem } from "@headlessui/vue";
import { ChevronDownIcon } from "@heroicons/vue/solid";
import { ref } from "vue";

export default {
  components: {
    Menu,
    MenuButton,
    MenuItems,
    MenuItem,
    ChevronDownIcon,
  },
  setup() {
    const menu = ref([
      [{ label: "edit" }, { label: "duplicate" }],
      [{ label: "archive" }, { label: "move" }],
      [{ label: "delete", disabled: true }],
    ]);

    return {
      menu,
    };
  },
};
</script>
