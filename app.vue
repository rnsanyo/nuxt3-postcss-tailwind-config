<template>
  <div class="container mx-auto px-4">
    <nav class="flex justify-between items-center py-4">
      <div class="text-2xl font-bold">Logo</div>
      <div>
        <router-link to="/" class="px-2">Home</router-link>
        <router-link to="/about" class="px-2">About</router-link>
      </div>
    </nav>
    <header class="text-center py-10">
      <h1 class="text-5xl font-bold">Welcome to Our Site</h1>
      <p class="text-xl">This is a demonstration of how to use Tailwind CSS with PostCSS in Nuxt 3.</p>
    </header>
    <section>
      <h2 class="text-4xl font-bold text-center my-8">Our Services</h2>
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
        <figure class="card" v-for="service in services" :key="service.id">
          <div class="img-bg"></div>
          <svg xmlns="http://www.w3.org/2000/svg"  viewBox="0 0 50 50" width="500px" height="500px"><path d="M 14 3 C 12.35503 3 11 4.3550302 11 6 L 11 21.025391 C 6.5553849 21.287845 3 24.992242 3 29.5 A 1.50015 1.50015 0 1 0 6 29.5 C 6 26.613798 8.1829785 24.273812 11 24.023438 L 11 37 C 11 38.64497 12.35503 40 14 40 L 18 40 L 18 45.5 A 1.50015 1.50015 0 1 0 21 45.5 L 21 40 L 29 40 L 29 45.5 A 1.50015 1.50015 0 1 0 32 45.5 L 32 40 L 36 40 C 37.64497 40 39 38.64497 39 37 L 39 23.974609 C 43.444615 23.712155 47 20.007758 47 15.5 A 1.50015 1.50015 0 0 0 45.476562 13.978516 A 1.50015 1.50015 0 0 0 44 15.5 C 44 18.386202 41.817022 20.726188 39 20.976562 L 39 6 C 39 4.3550302 37.64497 3 36 3 L 14 3 z M 14 5 L 36 5 C 36.56503 5 37 5.4349698 37 6 L 37 22.253906 A 1.50015 1.50015 0 0 0 37 22.740234 L 37 37 C 37 37.56503 36.56503 38 36 38 L 14 38 C 13.43497 38 13 37.56503 13 37 L 13 22.746094 A 1.50015 1.50015 0 0 0 13 22.259766 L 13 6 C 13 5.4349698 13.43497 5 14 5 z M 17 7 C 15.906937 7 15 7.9069372 15 9 L 15 18 C 15 19.093063 15.906937 20 17 20 L 33 20 C 34.093063 20 35 19.093063 35 18 L 35 9 C 35 7.9069372 34.093063 7 33 7 L 17 7 z M 17 9 L 33 9 L 33 18 L 17 18 L 17 9 z M 20 11 A 1 1 0 0 0 20 13 A 1 1 0 0 0 20 11 z M 30 11 A 1 1 0 0 0 30 13 A 1 1 0 0 0 30 11 z M 23 14 C 23 15.105 23.895 16 25 16 C 26.105 16 27 15.105 27 14 L 23 14 z M 15 22 L 15 24 L 27 24 L 27 22 L 15 22 z M 32 22 A 1 1 0 0 0 32 24 A 1 1 0 0 0 32 22 z M 17 26 L 17 28 L 15 28 L 15 30 L 17 30 L 17 32 L 19 32 L 19 30 L 21 30 L 21 28 L 19 28 L 19 26 L 17 26 z M 29 26 L 27 29 L 31 29 L 29 26 z M 34 27 C 33.448 27 33 27.448 33 28 C 33 28.552 33.448 29 34 29 C 34.552 29 35 28.552 35 28 C 35 27.448 34.552 27 34 27 z M 31.5 31 C 30.119 31 29 32.119 29 33.5 C 29 34.881 30.119 36 31.5 36 C 32.881 36 34 34.881 34 33.5 C 34 32.119 32.881 31 31.5 31 z M 16 34 A 1.0001 1.0001 0 1 0 16 36 L 18 36 A 1.0001 1.0001 0 1 0 18 34 L 16 34 z M 22 34 A 1.0001 1.0001 0 1 0 22 36 L 24 36 A 1.0001 1.0001 0 1 0 24 34 L 22 34 z"/></svg>
          <div class="card-content">
            <h3 class="card-title">{{ service.title }}</h3>
            <p class="card-description">{{ service.description }}</p>
          </div>
        </figure>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  data() {
    return {
      services: [
        { id: 1, title: 'Service 1', description: 'This is service 1' },
        { id: 2, title: 'Service 2', description: 'This is service 2' },
        { id: 3, title: 'Service 3', description: 'This is service 3' }
      ]
    };
  }
}
</script>

<style scoped>
figure {
  @apply my-auto flex relative flex-col;
}

figure svg, figure .img-bg {
  @apply w-64 h-64 md:w-80 md:h-80;
}

figure .img-bg {
  @apply absolute z-[-1] rounded-full blur-[50px] transition-all;
  animation: pulse 5s cubic-bezier(0, 0, 0, 0.5) infinite, glow 5s linear infinite, color-shift 10s infinite;
}

@keyframes pulse {
  0% { opacity: 1; }
  50% { opacity: 0.5; }
  100% { opacity: 1; }
}

@keyframes glow {
  0% { box-shadow: 0 0 5px #ff0000, 0 0 10px #ff0000, 0 0 15px #ff0000, 0 0 20px #ff0000; }
  50% { box-shadow: 0 0 10px #ff0000, 0 0 20px #ff0000, 0 0 30px #ff0000, 0 0 40px #ff0000; }
  100% { box-shadow: 0 0 5px #ff0000, 0 0 10px #ff0000, 0 0 15px #ff0000, 0 0 20px #ff0000; }
}

@keyframes color-shift {
  0% { background-color: #f00; }  /* red */
  25% { background-color: #0f0; } /* green */
  50% { background-color: #00f; } /* blue */
  75% { background-color: #0ff; } /* cyan */
  100% { background-color: #f00; } /* red again to complete the loop */
}

.card-content {
  @apply p-4;
  @apply bg-white bg-opacity-80; /* semi-transparent white background */
}

.card-title {
  @apply text-xl font-bold mb-2;
}

.card-description {
  @apply text-gray-700 text-base;
}
</style>

