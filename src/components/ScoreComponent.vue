<script lang="ts" setup>
interface Score {
  category: string,
  score: number,
  icon: string
}
defineProps<{
  score: Score,
}>();
</script>

<template>
  <div
    class="c-score"
    :class="{
      'is-reaction' : score.category === 'Reaction',
      'is-memory' : score.category === 'Memory',
      'is-verbal' : score.category === 'Verbal',
      'is-visual' : score.category === 'Visual',
    }"
  >
    <img :src="score.icon" alt="" class="c-score__image">
    <p class="c-score__category">{{ score.category }}</p>
    <p class="c-score__value">{{ score.score }} <span class="c-score__ref">/ 100</span></p>
  </div>
</template>