<template>
  <div
    class="w-fit m-auto my-2 bg-gray-300 bg-opacity-30 backdrop-blur-md rounded-lg p-3"
  >
    <input
      placeholder="id"
      type="text"
      :value="passwords_data.id"
      class="bg-gray-300 bg-opacity-30 backdrop-blur-md w-10 text-center border-0 p-2 m-2 rounded-lg text-xl"
    />
    <input
      placeholder="site"
      type="text"
      :value="passwords_data.site"
      class="bg-gray-300 bg-opacity-30 backdrop-blur-md border-0 p-2 m-2 rounded-lg text-xl"
    />
    <input
      placeholder="login"
      type="text"
      :value="passwords_data.login"
      class="bg-gray-300 bg-opacity-30 backdrop-blur-md border-0 p-2 m-2 rounded-lg text-xl"
    />
    <input
      placeholder="password"
      type="text"
      :value="passwords_data.password"
      class="bg-gray-300 bg-opacity-30 backdrop-blur-md border-0 p-2 m-2 rounded-lg text-xl"
    />
    <button
      type="button"
      @click="$emit('remove', passwords_data.id)"
      class="bg-gray-300 bg-opacity-30 backdrop-blur-md p-2 rounded-lg"
    >
      remove
    </button>
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  props: {
    passwords_data: {
      id: Number,
      site: String,
      login: String,
      password: String,
    },
  },

  setup() {
    return {};
  },
};
</script>

<style lang="scss" scoped></style>
