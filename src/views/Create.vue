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
         return;
      }
      exercises.value.push({
        id: uid(),
        cardioType: "",
        distance: "",
        duration: "",
        pace: "",
      });
    }
    

    // Delete exercise
    const deleteExercise = (id) => {
       if (exercises.value.length > 1) {
        exercises.value = exercises.value.filter((exercise) => exercise.id !== id);
        return;
      }
      errorMsg.value = "Error: Cannot remove, need to at least have one exercise";
      setTimeout(() => {
        errorMsg.value = false;
      }, 5000);
      
    }

    // Listens for chaging of workout type input

    // Create workout

    return {};
  },
};
</script>
