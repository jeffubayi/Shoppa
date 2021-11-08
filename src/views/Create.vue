<template>
  <div></div>
</template>

<script>
import {ref} from "vue";
import { uid } from "uid";
export default {
  name: "create",
  setup() {
    // Create data
    const workoutName = ref("");
    const workoutType = ref("select-workout");
    const exercises = ref([]);
    const statusMsg = ref(null);
    const errorMsg = ref(null);

    // Add exercise
    const addExcercise = () => {
      if(workoutType.value == "strength"){
         exercises.value.push({
          id: uid(),
          exercise: "",
          sets: "",
          reps: "",
          weight: "",
         })
      }
    }
    

    // Delete exercise

    // Listens for chaging of workout type input

    // Create workout

    return {};
  },
};
</script>
