<template>
  <v-sheet class="mx-auto">
    <v-form validate-on="submit lazy" @submit.prevent="onSubmit"   >
        <v-sheet><v-text-field id="to-do-input" label="item" v-model.lazy.trim="label" :rules="rules">
          </v-text-field></v-sheet>
         <v-sheet><v-btn type="submit" size="large" width="90%">Add</v-btn></v-sheet>
    </v-form>
  </v-sheet>
</template>
<script>
export default {
  methods: {
    onSubmit() {

      if (this.label == "") {
        console.log("nn");
        return;
      }
      this.$emit("todo-added", this.label);
      this.label = "";
    },
  },
  data() {
    return {
      label: "",
      rules: [
        value => {
          if (value) return true

          return 'You must enter a first name.'
        },
      ],
    };

  },
};
</script>