<template>
  <header
    class="bg-gray-900 sm:flex sm:justify-between sm:items-center sm:px-4 sm:py-3"
  >
    <div class="flex px-4 py-3 sm:p-0 items-center justify-between">
      <div class="flex items-center justify-center">
        <img class="h-16" src="/corona.png" alt="workcation" />
        <h1 class="ml-2 text-3xl font-semibold text-orange-500 pt-2">
          Corona Live Update
        </h1>
      </div>
      <div class="sm:hidden">
        <button
          @click="isOpen = !isOpen"
          type="button"
          class="block text-gray-500 hover:text-white focus:text-white focus:outline-none"
        >
          <svg class="h-6 w-6 fill-current" viewBox="0 0 24 24">
            <path
              v-if="isOpen"
              fill-rule="evenodd"
              d="M18.278 16.864a1 1 0 0 1-1.414 1.414l-4.829-4.828-4.828 4.828a1 1 0 0 1-1.414-1.414l4.828-4.829-4.828-4.828a1 1 0 0 1 1.414-1.414l4.829 4.828 4.828-4.828a1 1 0 1 1 1.414 1.414l-4.828 4.829 4.828 4.828z"
            />

            <path
              v-if="!isOpen"
              fill-rule="evenodd"
              d="M4 5h16a1 1 0 0 1 0 2H4a1 1 0 1 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2z"
            />
          </svg>
        </button>
      </div>
    </div>
    <!-- Toggle elements -->
    <nav :class="isOpen ? 'block' : 'hidden'" class="sm:block">
      <div class="px-2 pt-2 pb-4 sm:flex sm:p-0">
        <a
          href="#"
          class="block px-2 py-1 hover:bg-gray-700 font-semibold rounded text-white"
          >Home</a
        >
      </div>
    </nav>
  </header>
</template>

<script>
export default {
  data() {
    return {
      isOpen: false,
    };
  },
};
</script>

<style lang="stylus" scoped></style>
