<template>
  <main>
    <div class="row mt-5">
      <div class="col-12 col-md-6 mx-auto">
        <h3 class="text-center" style="font-weight: bold">
          overall satisfaction
        </h3>

        <StarRating
          v-model="rating"
          read-only
          :show-rating="false"
          :rating="4"
          :glow="2"
        />
        <p class="text-center font-bold mt-3">
          {{ `${rating}/${maxRating}` }}
        </p>
      </div>
      <div class="col-12 mt-2">
        <div class="mb-3">
          <label for="review" class="form-label">
            please add a short review</label
          >
          <textarea
            :maxlength="maxlength"
            class="form-control"
            id="review"
            rows="5"
            v-model="review"
          ></textarea>
          <p class="d-flex justify-content-end">
            <span> {{ review.length }}</span>
            <span> /</span>
            <span> {{ maxlength }}</span>
          </p>
        </div>
      </div>
      <div class="col-12">
        <div class="d-grid gap-2">
          <button
            class="btn btn-primary"
            type="button"
            @click="$emit('handle-next')"
          >
            next
          </button>
        </div>
      </div>
    </div>
  </main>
</template>

<script>
import StarRating from "vue-star-rating";

export default {
  name: "FirstStep",
  components: {
    StarRating,
  },
  data() {
    return {
      rating: 4,
      maxRating: 5,
      maxlength: 1080,
      review: "",
    };
  },
};
</script>

<style>
</style>