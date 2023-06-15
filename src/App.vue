<script setup lang="ts">
import ScoreComponent from './components/ScoreComponent.vue';

interface Score {
  category: string,
  score: number,
  icon: string
}

const scores: Score[] = [
  {
    category: 'Reaction',
    score: 80,
    icon: './assets/icon-reaction.svg'
  },
  {
    category: 'Memory',
    score: 92,
    icon: './assets/icon-memory.svg'
  },
  {
    category: 'Verbal',
    score: 61,
    icon: './assets/icon-verbal.svg'
  },
  {
    category: 'Visual',
    score: 72,
    icon: './assets/icon-visual.svg'
  }
]
</script>

<template>
  <main>
    <div class="c-report-card">
      <div class="c-report-card__section c-report-card__section--result">
        <h1>Your Result</h1>
        <div class="c-score-circle">
          <strong class="c-score-circle__score">76</strong>
          of 100
        </div>
        <strong>Great</strong>
        <p>You scored higher than 65% of the people who have taken these tests.</p>
      </div>
      <div class="c-report-card__section c-report-card__section--summary">
        <h2>Summary</h2>
        <ScoreComponent
          v-for="score in scores"
          :key="score.category"
          :score="score"
        />
        <button class="c-btn" type="button">Continue</button>
      </div>
    </div>
  </main>
</template>