<template>
  <Listbox v-model="selectedPerson" horizontal>
    <ListboxButton>{{ selectedPerson.name }}</ListboxButton>

    <ListboxOptions class="flex flex-row">
      <ListboxOption
        v-for="person in people"
        :key="person"
        :value="person"
        class="px-2"
        v-slot="{ active, selected }"
      >
        <span :class="{ 'text-green-500': selected && !active, 'text-blue-500': active }">
          {{ person.name }} {{ active }} {{ selected }}
        </span>
      </ListboxOption>
    </ListboxOptions>
  </Listbox>
</template>

<script>
import { ref } from "vue";
import {
  Listbox,
  ListboxButton,
  ListboxOptions,
  ListboxOption,
} from "@headlessui/vue";

export default {
  components: { Listbox, ListboxButton, ListboxOptions, ListboxOption },

  setup() {
    const people = [
      { id: 1, name: "Durward Reynolds" },
      { id: 2, name: "Kenton Towne" },
      { id: 3, name: "Therese Wunsch" },
      { id: 4, name: "Benedict Kessler" },
      { id: 5, name: "Katelyn Rohan" },
    ];
    const selectedPerson = ref(people[0]);

    return {
      people,
      selectedPerson,
    };
  },
};
</script>
