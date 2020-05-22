<template>
  <div
    class="w-full max-w-xl sm:w-64 sm:h-40 sm:m-4 rounded-lg shadow-lg shadow-gray-900"
  >
    <div class="p-4 pt-6">
      <div class="border-b border-gray-300 mb-4">
        <h1
          class="flex justify-center items-center font-semibold text-2xl mb-4"
        >
          {{ name }}
        </h1>
      </div>
      <span class=""></span>
      <h1 class="flex justify-center items-center font-bold text-2xl ">
        {{ info }}
      </h1>
    </div>
  </div>
</template>

<script>
export default {
  props: ["info", "name"],
};
</script>

<style lang="scss" scoped></style>
