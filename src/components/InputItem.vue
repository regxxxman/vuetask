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

  <div class="absolute flex inset-x-0 bottom-0 w-fit mx-auto mb-2">
    <!-- <input
      type="text"
      placeholder="find on site.com"
      class="bg-gray-600 p-3 text-3xl rounded-lg border-0 focus-visible:border-0 text-center"
    /> -->
    <input
      type="text"
      placeholder="Site find.."
      class="input input-ghost w-full bg-transparent max-w-xs"
    />
    <div class="dropdown dropdown-top dropdown-end">
      <label tabindex="0" class="btn btn-ghost m-1"
        ><span class="material-symbols-rounded"> add </span></label
      >
      <ul
        tabindex="0"
        class="dropdown-content menu p-2 shadow bg-base-100 bg-opacity-50 backdrop-blur-md rounded-box w-52"
      >
        <li>
          <input
            type="text"
            placeholder="Enter login.."
            class="input input-ghost w-full max-w-xs bg-transparent"
            v-model="inputlogin"
          />
        </li>
        <li>
          <input
            type="text"
            placeholder="Enter password.."
            class="input input-ghost w-full max-w-xs bg-transparent"
            v-model="inputpassword"
          />
        </li>

        <li>
          <button
            @click="
              $emit('add', inputlogin, inputpassword);
              cleaninput();
            "
            class="btn bg-gray-600 hover:bg-gray-700 border-gray-700 hover:border-gray-600 border-2"
          >
            Add
          </button>
        </li>
      </ul>
    </div>
    <!-- <button
      class="bg-gray-600 p-3 text-3xl rounded-lg ml-2 hover:scale-125 ease-in duration-100 active:bg-red-500 active:scale-50"
      @click="$emit('add', 'login', 'pass')"
    >
      add
    </button> -->
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  setup() {
    const inputlogin = ref();
    const inputpassword = ref();
    const cleaninput = ref(() => {
      inputlogin.value = "";
      inputpassword.value = "";
    });
    return { inputlogin, inputpassword, cleaninput };
  },
};
</script>

<style lang="scss" scoped>
@import "https://fonts.googleapis.com/css2?family=Material+Symbols+Rounded:opsz,wght,FILL,GRAD@20..48,100..700,0..1,-50..200";
.material-symbols-rounded {
  font-variation-settings: "FILL" 0, "wght" 400, "GRAD" 0, "opsz" 48;
  font-size: 2rem;
}
</style>
