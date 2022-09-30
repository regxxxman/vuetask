<template>
  <main class="bg-gray-800 text-white min-w-screen min-h-screen">
    <div class="h-10"></div>
    <div class="flex items-center justify-center">
      <transition-group
        class="scrollContainer rounded-lg overflow-y-auto w-fit scroll-smooth scrollbar-thin scrollbar-thumb-gray-700 scrollbar-track-gray-600 scrollbar-thumb-rounded-full scrollbar-track-rounded-full"
        name="list-complete"
        tag="div"
        id="scrollContainer"
      >
        <div
          v-for="itempass in passwords"
          :key="itempass.id"
          class="list-complete-item"
          ref="itemRefs"
        >
          <card-item
            :passwords_data="itempass"
            :id="
              itempass.id == passwords[passwords.length - 1].id ? 'last' : null
            "
            @remove="remove"
          />
        </div>
      </transition-group>

      <input-item @add="add" />
    </div>
  </main>
</template>

<script>
import { computed, onMounted, ref } from "vue";
import CardItem from "./components/CardItem.vue";
import InputItem from "./components/InputItem.vue";

export default {
  setup() {
    const passwords = ref([
      { id: 0, site: "vk.com", login: "reglog", password: "regpass" },
    ]);
    const remove = ref((id) => {
      for (let i = 0; i < passwords.value.length; i++) {
        if (passwords.value[i].id == id) {
          passwords.value.splice(i, 1);
        }
      }
    });
    const add = ref((login, password) => {
      passwords.value.push({
        id:
          passwords.value.length > 0
            ? passwords.value[passwords.value.length - 1].id + 1
            : 0,
        site: "vk.com",
        login: login ? login : "enter login",
        password: password ? password : "enter password",
      });
      setTimeout(() => {
        document.getElementById("last").scrollIntoView({ behavior: "smooth" });
      }, 100);
    });
    const info = ref(() => {
      console.log();
    });
    const scrollToElement = ref(() => {
      console.log("click");
    });

    const removeItem = ref((id) => {
      console.log("click remove", id);
    });

    const filterOnText = computed(() => {
      return;
    });
    return { passwords, remove, add, info, scrollToElement };
  },
  components: { CardItem, InputItem },
};
</script>

<style lang="scss" scoped>
.list-complete-item {
  transition: all 0.8s ease;
  margin-right: 10px;
}

.list-complete-enter-from,
.list-complete-leave-to {
  opacity: 0;
  transform: translateY(30px);
}

.list-complete-leave-active {
  position: absolute;
}

.scrollContainer {
  height: calc(100vh - 10rem);
}
</style>
