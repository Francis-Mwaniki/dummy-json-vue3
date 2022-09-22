<template>
  <div class="">
    <form
      @submit.prevent="handleSubmit"
      class="flex justify-center items-center flex-col mx-auto max-w-xl gap-y-2 bg-slate-100 border-emerald-200 border rounded-md"
    >
      <img
        src="@/assets/user.png"
        alt=""
        class="flex justify-center items-center mx-auto p-1 rounded-full bg-teal-500 pt-1"
      />

      <fieldset class="flex justify-center items-center">
        <legend class="font-mono text-black">First Name</legend>
        <input
          type="text"
          class="px-6 py-2 rounded-lg p-1 text-black m-1 border border-black"
          placeholder="Enter your First Name"
          v-model="fName"
        />
      </fieldset>

      <fieldset class="flex justify-center items-center sm:flex-row flex-col">
        <legend class="font-mono text-black">Age</legend>
        <input
          type="text"
          class="px-6 py-2 rounded-lg p-1 text-black m-1 border border-black"
          placeholder="Enter your age"
          v-model="age"
        />
      </fieldset>
      <fieldset class="flex justify-center items-center sm:flex-row flex-col">
        <legend class="font-mono text-black">Last Name</legend>
        <input
          type="text"
          class="px-6 py-2 rounded-lg p-1 text-black m-1 border border-black"
          placeholder="Enter your last Name"
          v-model="lName"
        />
      </fieldset>
      <fieldset class="flex justify-center items-center sm:flex-row flex-col">
        <legend class="font-mono text-black">Email</legend>
        <input
          type="email"
          class="px-6 py-2 rounded-lg p-1 text-black m-1 border border-black"
          placeholder="Enter your email"
          v-model="email"
          required="required"
        />
      </fieldset>
      <input
        type="submit"
        class="px-6 py-2 rounded-lg p-1 bg-indigo-600 text-white m-1 border border-black bg"
        value="Submit"
      />
    </form>
    <div
      v-show="data"
      class="flex flex-col justify-center items-center mx-auto p-2 max-w-xl bg-orange-600 text-black rounded-md border-emerald-400 border"
    >
      <h4 class="font-extrabold">Output Data</h4>
      <fieldset class="flex justify-center items-center flex-col">
        <h5>{{ fName }}</h5>
        <h5>{{ lName }}</h5>
        <h5>{{ email }}</h5>
        <h5>{{ age }}</h5>
      </fieldset>
    </div>
  </div>
</template>

<script>
export default {
  name: "Form",
  data() {
    return {
      fName: "",
      lName: "",
      email: "",
      age: "",
      data: false,
    };
  },
  methods: {
    handleSubmit() {
      this.data = true;
      console.log(this.fName, this.lName, this.email, this.age);
    },
  },
};
</script>

<style></style>
