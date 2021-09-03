<template>
  <div class="alert alert-primary">
    <h2>{{ title }}</h2>
    <p>{{ message }}</p>
    <hr />
    <p class="h5">val:{{ val }}</p>
    <div class="form-group text-left">
      <label for="">*2:</label>
      <input type="number" v-model="a" class="form-control" />
    </div>
    <div class="group-form text-left">
      <label>^ 2:</label>
      <input type="number" v-model="b" class="form-control" />
    </div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    title: String,
    num: {
      type: Number,
      default: 100,
      validator: (value) => {
        return value == parseInt(value) && value >= 0 && value <= 100;
      },
    },
  },
  data() {
    return {
      message: "バリデーション・チェック",
    };
  },
};
</script>
