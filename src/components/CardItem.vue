<template>
  <ul>
    <li>id: {{ itempass.id }}</li>
    <li>login: {{ itempass.login }}</li>
    <li>password: {{ itempass.password }}</li>
    <!-- <button @click="remove(itempass)" class="bg-gray-700 p-3 rounded-lg">
      remove
    </button> -->
  </ul>
</template>

<script>
export default {
  setup(itempass) {
    return {};
  },
};
</script>

<style lang="scss" scoped></style>
