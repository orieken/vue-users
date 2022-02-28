<template>
  <div class="flex justify-center gap-4">
    <ul class="bg-white rounded-lg border border-gray-200 w-96 text-gray-900">
      <li class="px-6 py-2 borderb border-gray-200 w-full">
        <div
          v-for="user in users"
          :key="user.id"
          :id="user.id"
          class="space-x-4"
        >
          <img
            class="w-3/4 rounded"
            v-bind:src="user.image"
            v-bind:alt="user.name"
          />
          <div class="relative px-6 -mt-16">
            <div class="bg-white p-4 rounded-lg shadow-lg">
              <div class="flex items-baseline">
                <span
                  class="bg-teal-200 text-teal-800 text-xs px-2 inline-block rounded-full uppercase font-semibold stracking-wide"
                >
                  {{ user.status }}
                </span>
                <div
                  class="ml-2 text-gray-600 uppercase text-xs font-semibold tracking-wider"
                >
                  details
                </div>
              </div>
              <h4
                class="mt-1 text-xl font-semibold uppercase leading-tight truncate"
              >
                {{ user.name }}
              </h4>
              <div class="mt-1">
                <span class="text-gray-600 text-sm">blank?</span>
              </div>
              <div class="mt-4">
                <span class="text-teal-600 text-md font-semibold">
                  {{ user.species }}
                </span>
                <span class="text-sm text-gray-600">({{ user.gender }})</span>
              </div>
            </div>
          </div>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "get-users",
  data() {
    return { users: undefined };
  },
  async created() {
    const response = await axios.get(
      "https://tranquil-harbor-61934.herokuapp.com/users"
    );
    console.log(response.data);
    this.users = response.data;
  },
};
</script>
<style scoped></style>
