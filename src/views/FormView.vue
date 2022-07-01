<template>
  <div class="form">
    <SignupForm />
  </div>
</template>
<script>
import SignupForm from "@/components/SignupForm.vue";
export default {
  name: "FormView",
  components: {SignupForm}
}
</script>
<style>
  body{
    background-color:grey;
  }
</style>
