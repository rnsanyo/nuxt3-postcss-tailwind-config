<template>
  <div class="main-div">
    <h1>Page Title</h1>
    <h2>Page subtitle 2</h2>
    <h3>Page subtitle 3</h3>
  </div>
</template>

<style lang="postcss">
.main-div {
  h1 {
    @apply !text-5xl md:!text-6xl max-w-[600px];
  }
  h2 {
    @apply text-red-300
  }
}
</style>