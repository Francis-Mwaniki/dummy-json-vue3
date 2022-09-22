<template>
  <div class="flex flex-col mt-2">
    <h2
      class="flex flex-row justify-center items-center mx-auto text-2xl font-mono font-extrabold uppercase"
    >
      Dummy data
    </h2>
    <div class="overflow-x-auto sm:-mx-6 lg:-mx-8">
      <div class="py-2 inline-block min-w-full sm:px-6 lg:px-8">
        <div class="overflow-hidden">
          <table class="min-w-full">
            <thead class="border-b">
              <tr>
                <th
                  scope="col"
                  class="text-sm font-medium text-gray-900 px-6 py-4 text-left"
                >
                  ID
                </th>
                <th
                  scope="col"
                  class="text-sm font-medium text-gray-900 px-6 py-4 text-left"
                >
                  RATINGS
                </th>
                <th
                  scope="col"
                  class="text-sm font-medium text-gray-900 px-6 py-4 text-left"
                >
                  PRICE
                </th>
                <th
                  scope="col"
                  class="text-sm font-medium text-gray-900 px-6 py-4 text-left"
                >
                  STOCKS
                </th>
              </tr>
            </thead>
            <tbody v-for="product in resources[0]">
              <tr class="bg-white border-b" v-for="p in product">
                <td class="px-6 py-4 whitespace-nowrap text-sm font-medium text-gray-900">
                  {{ p.id }}
                </td>
                <td
                  class="text-sm text-gray-900 font-light px-6 py-4 whitespace-nowrap border-b bg-yellow-200 border-yellow-200"
                >
                  {{ p.rating }}
                </td>
                <td
                  class="text-sm text-gray-900 font-light px-6 py-4 whitespace-nowrap bg-slate-300 border-emerald-400"
                >
                  {{ p.price }}
                </td>
                <td
                  class="text-sm text-gray-900 font-light px-6 py-4 whitespace-nowrap bg-indigo-300 border-b-black"
                >
                  {{ p.stock }}
                </td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Resources",
  data() {
    return {
      resources: [],
    };
  },
  mounted() {
    this.fetchAllProducts();
  },
  methods: {
    async fetchAllProducts() {
      const res = await fetch("https://dummyjson.com/products/?limit=500");
      const json = await res.json();
      this.resources.push(json);
      console.log(this.resources[0].products[0]);
    },
  },
};
</script>

<style></style>
