<script>
import BaseSwitch from "@/components/BaseSwitch.vue";
import BaseSwitchGroup from "@/components/BaseSwitchGroup.vue";
import BaseDropdown from "@/components/BaseDropdown.vue";
import BaseListBox from "@/components/BaseListBox.vue";
import BaseDisclosure from "@/components/BaseDisclosure.vue";
import BaseTransition from "@/components/BaseTransition.vue";

export default {
  components: {
    BaseSwitch,
    BaseSwitchGroup,
    BaseDropdown,
    BaseListBox,
    BaseDisclosure,
    BaseTransition,
  },
};
</script>

<template>
  HELLO
  <BaseTransition />
  HELLO
  <div class="flex flex-col space-y-4">
    <BaseSwitch />
    <div>
      <BaseSwitchGroup />
    </div>
    <BaseDropdown />
    <BaseListBox />
    <BaseDisclosure />
  </div>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
