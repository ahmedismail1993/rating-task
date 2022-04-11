<template>
  <main>
    <div class="row mt-5">
      <h3 class="font-bold">Additional Ratings</h3>
      <div class="col-12">
        <div class="font-bold size-14">communications</div>

        <StarRating
          v-model="form.additional_rating"
          :show-rating="false"
          :rating="4"
          :glow="2"
          :star-size="20"
          :padding="5"
        />
      </div>
      <div class="col-12 my-3">
        <div class="font-bold size-14">quality of work</div>

        <StarRating
          v-model="form.quality_work_rating"
          :show-rating="false"
          :rating="4"
          :glow="2"
          :star-size="20"
          :padding="5"
        />
      </div>
      <div class="col-12">
        <div class="font-bold size-14">Value of money</div>

        <StarRating
          v-model="form.quality_value_money_rating"
          :show-rating="false"
          :rating="4"
          :glow="2"
          :star-size="20"
          :padding="5"
        />
      </div>

      <div class="col-12 mt-2">
        <div class="d-grid gap-2">
          <button class="btn btn-primary" type="button">send feedback</button>
        </div>
      </div>
    </div>
  </main>
</template>

<script>
import StarRating from "vue-star-rating";

export default {
  name: "Second",
  components: {
    StarRating,
  },
  data() {
    return {
      form: {
        additional_rating: 0,
        quality_work_rating: 0,
        quality_value_money_rating: 0,
      },
      maxRating: 5,
      maxlength: 1080,
      review: "",
    };
  },
};
</script>

<style>
</style>