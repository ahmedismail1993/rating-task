<template>
  <div class="container">
    <div class="row">
      <div class="col-12 col-md-6 mx-auto mt-5">
        <div class="card p-5">
          <div class="row">
            <div class="col-12">
              <h4>Your Review of Circle Design</h4>
            </div>
            <div class="col-12 col-md-10">
              <p>
                please review the work done by circle design for the project
                <q
                  >Build site with apointment functionality linked to shopify</q
                >
              </p>
            </div>
          </div>
          <transition name="fade" mode="out-in">
            <component
              :is="components[componentIndex]"
              @handle-next="componentIndex++"
            />
          </transition>
          <div class="col-12 text-center mt-2" v-if="componentIndex > 0">
            <div class="row">
              <div class="col-12 col-md-6 d-flex justify-content-start">
                <a @click="componentIndex = 0" class="primary--text">back</a>
              </div>
              <div class="col-12 col-md-6 d-flex justify-content-end">
                <a href="" class="primary--text">skip & send </a>
              </div>
            </div>
          </div>
          <div class="col-12 text-center mt-2">
            {{ `${componentIndex + 1}/${components.length}` }}
          </div>
          <div class="pagination">
            <span
              :class="[componentIndex == index ? 'active-step' : '']"
              v-for="(item, index) in components"
              :key="index"
              @click="componentIndex = index"
            ></span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import FirstStep from "./firstStep.vue";
import SecondStep from "./secondStep.vue";
export default {
  name: "Rating",
  components: {
    FirstStep,
    SecondStep,
  },
  data() {
    return {
      componentIndex: 0,
      components: ["FirstStep", "SecondStep"],
    };
  },
};
</script>

<style lang="scss">
* {
  font-family: "Cairo", sans-serif;
  font-family: "Roboto", sans-serif;
}
.card {
  box-shadow: 0 5px 10px #ccc;
}
textarea {
  resize: none;
  box-shadow: none !important;
}
.font-bold {
  font-weight: bold;
}
.pagination {
  display: flex;
  justify-content: center;
  span {
    display: inline-block;
    width: 10px;
    height: 10px;
    background-color: #ccc;
    border-radius: 50%;
    margin: 0 1px;
    cursor: pointer;
  }
}
.active-step {
  background-color: #0d6efd !important;
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
.size-14 {
  font-size: 14px !important;
}
a {
  text-decoration: none;
  cursor: pointer;
}
</style>