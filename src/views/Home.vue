<template>
  <div v-if="dataLoaded" class="container mt-10 px-4">
    <div class="carousel relative rounded relative overflow-hidden shadow-xl">
      <div class="carousel-inner relative overflow-hidden w-full">
        <!--Slide 1-->
        <input
          class="carousel-open"
          type="radio"
          id="carousel-1"
          name="carousel"
          aria-hidden="true"
          hidden=""
          checked="checked"
        />
        <div
          class="carousel-item absolute opacity-0 bg-contain bg-center"
          style="
            height: 500px;
            background-image: url(http://www.eatwell101.com/wp-content/uploads/2012/02/A-Beginner%E2%80%99s-Shopping-List.jpg);
          "
        ></div>
        <label
          for="carousel-3"
          class="
            control-1
            w-10
            h-10
            ml-2
            md:ml-10
            absolute
            cursor-pointer
            hidden
            font-bold
            text-black
            hover:text-white
            rounded-full
            bg-white
            hover:bg-at-light-green
            leading-tight
            text-center
            z-10
            inset-y-0
            left-0
            my-auto
            flex
            justify-center
            content-center
          "
          ><i class="fas fa-angle-left mt-3"></i
        ></label>
        <label
          for="carousel-2"
          class="
            next
            control-1
            w-10
            h-10
            mr-2
            md:mr-10
            absolute
            cursor-pointer
            hidden
            font-bold
            text-black
            hover:text-white
            rounded-full
            bg-white
            hover:bg-at-light-green
            leading-tight
            text-center
            z-10
            inset-y-0
            right-0
            my-auto
          "
          ><i class="fas fa-angle-right mt-3"></i
        ></label>

        <!--Slide 2-->
        <input
          class="carousel-open"
          type="radio"
          id="carousel-2"
          name="carousel"
          aria-hidden="true"
          hidden=""
        />
        <div
          class="carousel-item absolute opacity-0 bg-center bg-contain"
          style="
            height: 500px;
            background-image: url(https://media.istockphoto.com/photos/mother-and-daughter-grocery-shop-together-using-list-picture-id936496982?b=1&k=20&m=936496982&s=170667a&w=0&h=Ae3foPZghE7dTTZxGLDeIL939btPLuhgpyI79g97zJY=);
          "
        ></div>
        <label
          for="carousel-1"
          class="
            control-2
            w-10
            h-10
            ml-2
            md:ml-10
            absolute
            cursor-pointer
            hidden
            font-bold
            text-black
            hover:text-white
            rounded-full
            bg-white
            hover:bg-at-light-green
            leading-tight
            text-center
            z-10
            inset-y-0
            left-0
            my-auto
          "
          ><i class="fas fa-angle-left mt-3"></i
        ></label>
        <label
          for="carousel-3"
          class="
            next
            control-2
            w-10
            h-10
            mr-2
            md:mr-10
            absolute
            cursor-pointer
            hidden
            font-bold
            text-black
            hover:text-white
            rounded-full
            bg-white
            hover:bg-at-light-green
            leading-tight
            text-center
            z-10
            inset-y-0
            right-0
            my-auto
          "
          ><i class="fas fa-angle-right mt-3"></i
        ></label>

        <!--Slide 3-->
        <input
          class="carousel-open"
          type="radio"
          id="carousel-3"
          name="carousel"
          aria-hidden="true"
          hidden=""
        />
        <div
          class="carousel-item absolute opacity-0 bg-contain bg-center"
          style="
            height: 500px;
            background-image: url(https://media.baamboozle.com/uploads/images/78483/1612382332_131017);
          "
        ></div>
        <label
          for="carousel-2"
          class="
            control-3
            w-10
            h-10
            ml-2
            md:ml-10
            absolute
            cursor-pointer
            hidden
            font-bold
            text-black
            hover:text-white
            rounded-full
            bg-white
            hover:bg-at-light-green
            leading-tight
            text-center
            z-10
            inset-y-0
            left-0
            my-auto
          "
          ><i class="fas fa-angle-left mt-3"></i
        ></label>
        <label
          for="carousel-1"
          class="
            next
            control-3
            w-10
            h-10
            mr-2
            md:mr-10
            absolute
            cursor-pointer
            hidden
            font-bold
            text-black
            hover:text-white
            rounded-full
            bg-white
            hover:bg-at-light-green
            leading-tight
            text-center
            z-10
            inset-y-0
            right-0
            my-auto
          "
          ><i class="fas fa-angle-right mt-3"></i
        ></label>

        <!-- Add additional indicators for each slide-->
        <ol class="carousel-indicators">
          <li class="inline-block mr-3">
            <label
              for="carousel-1"
              class="
                carousel-bullet
                cursor-pointer
                block
                text-4xl text-white
                hover:text-at-light-green
              "
              >•</label
            >
          </li>
          <li class="inline-block mr-3">
            <label
              for="carousel-2"
              class="
                carousel-bullet
                cursor-pointer
                block
                text-4xl text-white
                hover:text-at-light-green
              "
              >•</label
            >
          </li>
          <li class="inline-block mr-3">
            <label
              for="carousel-3"
              class="
                carousel-bullet
                cursor-pointer
                block
                text-4xl text-white
                hover:text-at-light-green
              "
              >•</label
            >
          </li>
        </ol>
      </div>
    </div>

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

    <div
      class="carousel relative rounded relative overflow-hidden shadow-xl"
      v-else
    >
      <div class="carousel-inner relative overflow-hidden w-full">
        <!--Slide 1-->
        <input
          class="carousel-open"
          type="radio"
          id="carousel-1"
          name="carousel"
          aria-hidden="true"
          hidden=""
          checked="checked"
        />
        <div
          class="carousel-item absolute opacity-0 bg-contain bg-center"
          style="
            height: 500px;
            background-image: url(http://www.eatwell101.com/wp-content/uploads/2012/02/A-Beginner%E2%80%99s-Shopping-List.jpg);
          "
        ></div>
        <label
          for="carousel-3"
          class="
            control-1
            w-10
            h-10
            ml-2
            md:ml-10
            absolute
            cursor-pointer
            hidden
            font-bold
            text-black
            hover:text-white
            rounded-full
            bg-white
            hover:bg-at-light-green
            leading-tight
            text-center
            z-10
            inset-y-0
            left-0
            my-auto
            flex
            justify-center
            content-center
          "
          ><i class="fas fa-angle-left mt-3"></i
        ></label>
        <label
          for="carousel-2"
          class="
            next
            control-1
            w-10
            h-10
            mr-2
            md:mr-10
            absolute
            cursor-pointer
            hidden
            font-bold
            text-black
            hover:text-white
            rounded-full
            bg-white
            hover:bg-at-light-green
            leading-tight
            text-center
            z-10
            inset-y-0
            right-0
            my-auto
          "
          ><i class="fas fa-angle-right mt-3"></i
        ></label>

        <!--Slide 2-->
        <input
          class="carousel-open"
          type="radio"
          id="carousel-2"
          name="carousel"
          aria-hidden="true"
          hidden=""
        />
        <div
          class="carousel-item absolute opacity-0 bg-center bg-contain"
          style="
            height: 500px;
            background-image: url(https://media.istockphoto.com/photos/mother-and-daughter-grocery-shop-together-using-list-picture-id936496982?b=1&k=20&m=936496982&s=170667a&w=0&h=Ae3foPZghE7dTTZxGLDeIL939btPLuhgpyI79g97zJY=);
          "
        ></div>
        <label
          for="carousel-1"
          class="
            control-2
            w-10
            h-10
            ml-2
            md:ml-10
            absolute
            cursor-pointer
            hidden
            font-bold
            text-black
            hover:text-white
            rounded-full
            bg-white
            hover:bg-at-light-green
            leading-tight
            text-center
            z-10
            inset-y-0
            left-0
            my-auto
          "
          ><i class="fas fa-angle-left mt-3"></i
        ></label>
        <label
          for="carousel-3"
          class="
            next
            control-2
            w-10
            h-10
            mr-2
            md:mr-10
            absolute
            cursor-pointer
            hidden
            font-bold
            text-black
            hover:text-white
            rounded-full
            bg-white
            hover:bg-at-light-green
            leading-tight
            text-center
            z-10
            inset-y-0
            right-0
            my-auto
          "
          ><i class="fas fa-angle-right mt-3"></i
        ></label>

        <!--Slide 3-->
        <input
          class="carousel-open"
          type="radio"
          id="carousel-3"
          name="carousel"
          aria-hidden="true"
          hidden=""
        />
        <div
          class="carousel-item absolute opacity-0 bg-contain bg-center"
          style="
            height: 500px;
            background-image: url(https://media.baamboozle.com/uploads/images/78483/1612382332_131017);
          "
        ></div>
        <label
          for="carousel-2"
          class="
            control-3
            w-10
            h-10
            ml-2
            md:ml-10
            absolute
            cursor-pointer
            hidden
            font-bold
            text-black
            hover:text-white
            rounded-full
            bg-white
            hover:bg-at-light-green
            leading-tight
            text-center
            z-10
            inset-y-0
            left-0
            my-auto
          "
          ><i class="fas fa-angle-left mt-3"></i
        ></label>
        <label
          for="carousel-1"
          class="
            next
            control-3
            w-10
            h-10
            mr-2
            md:mr-10
            absolute
            cursor-pointer
            hidden
            font-bold
            text-black
            hover:text-white
            rounded-full
            bg-white
            hover:bg-at-light-green
            leading-tight
            text-center
            z-10
            inset-y-0
            right-0
            my-auto
          "
          ><i class="fas fa-angle-right mt-3"></i
        ></label>

        <!-- Add additional indicators for each slide-->
        <ol class="carousel-indicators">
          <li class="inline-block mr-3">
            <label
              for="carousel-1"
              class="
                carousel-bullet
                cursor-pointer
                block
                text-4xl text-white
                hover:text-at-light-green
              "
              >•</label
            >
          </li>
          <li class="inline-block mr-3">
            <label
              for="carousel-2"
              class="
                carousel-bullet
                cursor-pointer
                block
                text-4xl text-white
                hover:text-at-light-green
              "
              >•</label
            >
          </li>
          <li class="inline-block mr-3">
            <label
              for="carousel-3"
              class="
                carousel-bullet
                cursor-pointer
                block
                text-4xl text-white
                hover:text-at-light-green
              "
              >•</label
            >
          </li>
        </ol>
      </div>
    </div>
    <div
      class="
        grid grid-cols-1
        sm:grid-cols-2
        md:grid-cols-3
        lg:grid-cols-3
        gap-6
      "
    >
      <router-link
        class="flex flex-col items-center p-8 cursor-pointer mb-3"
        :to="{ name: 'View-Workout', params: { workoutId: workout.id } }"
        v-for="(workout, index) in data"
        :key="index"
      >
        <!-- Card -->
        <div class="" style="width: 350px">
          <img
            src="https://www.lux-review.com/wp-content/uploads/2020/12/grocery-shopping.jpg"
            class="rounded-lg shadow-xl mb-4"
            alt=""
          />

          <div class="text-center">
            <h5 class="text-xl font-semibold mb-2">
              {{ workout.workoutName }}
            </h5>

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

            <button
              class="
                bg-at-light-green
                text-white
                active:bg-purple-600
                font-bold
                uppercase
                text-xs
                px-4
                py-2
                rounded
                shadow
                hover:shadow-md
                outline-none
                focus:outline-none
                mr-1
                mb-1
                ease-linear
                transition-all
                duration-150
              "
              type="button"
            >
              View list
            </button>
          </div>
        </div>
        <!-- Card -->
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

<!-- Required font awesome -->
<link
  rel="stylesheet"
  href="https://use.fontawesome.com/releases/v5.11.2/css/all.css"
/>
<style>
.carousel-open:checked + .carousel-item {
  position: static;
  opacity: 100;
}

.carousel-item {
  -webkit-transition: opacity 0.6s ease-out;
  transition: opacity 0.6s ease-out;
}

#carousel-1:checked ~ .control-1,
#carousel-2:checked ~ .control-2,
#carousel-3:checked ~ .control-3 {
  display: block;
}

.carousel-indicators {
  list-style: none;
  margin: 0;
  padding: 0;
  position: absolute;
  bottom: 2%;
  left: 0;
  right: 0;
  text-align: center;
  z-index: 10;
}

#carousel-1:checked
  ~ .control-1
  ~ .carousel-indicators
  li:nth-child(1)
  .carousel-bullet,
#carousel-2:checked
  ~ .control-2
  ~ .carousel-indicators
  li:nth-child(2)
  .carousel-bullet,
#carousel-3:checked
  ~ .control-3
  ~ .carousel-indicators
  li:nth-child(3)
  .carousel-bullet {
  color: #2b6cb0;
  /*Set to match the Tailwind colour you want the active one to be */
}
</style>
