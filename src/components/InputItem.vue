<template>
  <!-- <div class="absolute inset-x-0 bottom-0">
    <input
      ref="inputlogin"
      type="text"
      placeholder="login"
      class="bg-gray-700 border-0 rounded-lg text-xl"
    />
    <input
      ref="inputpassword"
      type="password"
      placeholder="password"
      class="bg-gray-700 border-0 rounded-lg text-xl"
    />

    <button
      type="button"
      @click="
        $emit(
          'add',
          this.$refs.inputlogin.value,
          this.$refs.inputpassword.value
        )
      "
      class="bg-gray-700 p-3 rounded-lg"
    >
      add
    </button>
    <button
      @click="scrollToElement"
      type="button"
      class="bg-gray-700 p-3 rounded-lg"
    >
      info
    </button>
  </div> -->

  <div class="absolute inset-x-0 bottom-0 w-fit mx-auto mb-2">
    <input
      type="text"
      placeholder="find on site.com"
      class="bg-gray-600 p-3 text-3xl rounded-lg border-0 focus-visible:border-0 text-center"
    />
    <button
      class="bg-gray-600 p-3 text-3xl rounded-lg ml-2 hover:scale-125 ease-in duration-100 active:bg-red-500 active:scale-50"
      @click="$emit('add', 'login', 'pass')"
    >
      add
    </button>
  </div>
</template>

<script>
export default {
  setup() {
    return {};
  },
};
</script>

<style lang="scss" scoped></style>
