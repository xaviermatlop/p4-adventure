<template>
  <div class="container">
    <h2>{{ story.text }}</h2>

    <!-- Huecos -->
    <div class="gaps">
      <div
        v-for="gap in story.gaps"
        :key="gap.id"
        class="gap"
        @dragover.prevent
        @drop="onDrop(gap.id)" > {{ userAnswers[gap.id] || "____" }}
      </div>
    </div>

    <div class="options">
      <div
        v-for="item in story.options"
        :key="item"
        class="option"
        draggable="true"
        @dragstart="onDragStart(item)" > {{ item }}
      </div>
    </div>
  </div>
</template>

<script setup>
const story = {
  text: "El héroe entró al bosque con su ____ y su ____.",
  gaps: [
    { id: 1, correct: "espada" },
    { id: 2, correct: "escudo" }
  ],
  options: ["espada", "escudo", "poción"]
}
</script>

<style>
  
</style>