<template>
  <main class="bg-gray-800 text-white min-w-screen min-h-screen">
    <div class="absolute inset-x-0 bottom-0 items-center flex">
      <input
        type="text"
        placeholder="find"
        class="mx-auto bg-gray-700 border-0 p-2 rounded-lg text-xl"
      />
    </div>

    <div class="">
      <div v-for="itempass in passwords" :key="itempass.id" class="list">
        <input
          type="text"
          :value="itempass.id"
          class="bg-gray-700 border-0 p-2 m-2 rounded-lg text-xl"
        />
        <input
          type="text"
          :value="itempass.site"
          class="bg-gray-700 border-0 p-2 m-2 rounded-lg text-xl"
        />
        <input
          type="text"
          :value="itempass.login"
          class="bg-gray-700 border-0 p-2 m-2 rounded-lg text-xl"
        />
        <input
          type="text"
          :value="itempass.password"
          class="bg-gray-700 border-0 p-2 m-2 rounded-lg text-xl"
        />
        <button @click="remove(itempass)" class="bg-gray-700 p-3 rounded-lg">
          remove
        </button>
        <button @click="remove(itempass)" class="bg-gray-700 p-3 rounded-lg">
          save
        </button>
      </div>
    </div>
    <input
      ref="inputlogin"
      type="text"
      placeholder="login"
      class="bg-gray-700 border-0 m-1 h-20 rounded-lg text-xl"
    />
    <input
      ref="inputpassword"
      type="password"
      placeholder="password"
      class="bg-gray-700 border-0 m-1 h-20 rounded-lg text-xl"
    />

    <button
      @click="add(this.$refs.inputlogin.value, this.$refs.inputpassword.value)"
      class="bg-gray-700 p-3 rounded-lg"
    >
      add
    </button>
    <button @click="info()" class="bg-gray-700 p-3 rounded-lg">info</button>
  </main>
</template>

<script>
import { ref } from "vue";
import CardItem from "./components/CardItem.vue";

export default {
  setup() {
    const passwords = ref([
      { id: 0, site: "vk.com", login: "reglog", password: "regpass" },
    ]);
    const remove = ref((id) => passwords.value.splice(id, 1));
    const add = ref((login, password) =>
      passwords.value.push({
        id:
          passwords.value.length > 0
            ? passwords.value[passwords.value.length - 1].id + 1
            : 0,
        site: "vk.com",
        login: login ? login : "enter login",
        password: password ? password : "enter password",
      })
    );
    const info = ref(() => {
      // console.log(passwords.value);
      // console.log(passwords.value[passwords.value.length - 1]);
      console.log(passwords.value);
    });
    return { passwords, remove, add, info };
  },
  components: { CardItem },
};
</script>

<style lang="scss" scoped></style>
