<template>
  <div v-if="dataLoaded" class="container mt-10 px-4">
    <!-- No Data -->
    <div v-if="data.length === 0" class="w-full flex flex-col items-center">
      <h1 class="text-2xl">Looks empty here...</h1>
      <router-link
        class="
          mt-6
          py-2
          px-6
          rounded-sm
          text-sm text-white
          bg-at-light-green
          duration-200
          border-solid border-2 border-transparent
          hover:border-at-light-green hover:bg-white hover:text-at-light-green
        "
        :to="{ name: 'Create' }"
        >Create Workout</router-link
      >
    </div>

    <!-- Data -->

    <div class="max-w-sm rounded overflow-hidden shadow-lg " v-else>
      <router-link
        class="
          flex flex-col
          items-center
          p-8
          shadow-md
          cursor-pointer
          mb-3
        "
        :to="{ name: 'View-Workout', params: { workoutId: workout.id } }"
        v-for="(workout, index) in data"
        :key="index"
      >
        <img
          class="w-full"
          src="https://www.lux-review.com/wp-content/uploads/2020/12/grocery-shopping.jpg"
          alt="Sunset in the mountains"
        />
        <div class="px-6 py-4">
          <div class="font-bold text-xl mb-2">{{ workout.workoutName }}</div>
        </div>
        <div class="px-6 pt-4 pb-2">
          <span
            class="
              inline-block
              bg-gray-200
              rounded-full
              px-3
              py-1
              text-sm
              font-semibold
              text-gray-700
              mr-2
              mb-2
            "
            ># {{ workout.workoutType }}</span
          >
        </div>
      </router-link>
    </div>
  </div>
</template>

<script>
import { ref } from "vue";
import { supabase } from "../supabase/init";
export default {
  name: "home",
  components: {},
  setup() {
    // Create data / vars
    const data = ref([]);
    const dataLoaded = ref(null);
    // Get data
    const getData = async () => {
      try {
        const { data: workouts, error } = await supabase
          .from("workouts")
          .select("*");
        if (error) throw error;
        data.value = workouts;
        dataLoaded.value = true;
      } catch (error) {
        console.warn(error.message);
      }
    };
    // Run data function
    getData();
    return { data, dataLoaded };
  },
};
</script>
