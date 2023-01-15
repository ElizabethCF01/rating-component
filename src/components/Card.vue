<template>
  <div class="card">
    <div v-if="!submited">
      <div class="card-header">
        <div class="icon">
          <img src="../assets/icon-star.svg" alt="Mi SVG feliz" />
        </div>
        <h1 class="title">How did we do?</h1>
      </div>
      <div class="card-body">
        <p class="description">
          Please let us know how we did with your support request. All feedback is appreciated
          to help us improve our offering!
        </p>
        <div class="card-actions">
          <div class="rating">
            <div @click="rate = i" class="circle" :class="rate == i ? 'selected' : ''" v-for="i in b" :key="i">
              <div>{{ i }}</div>
            </div>
          </div>
          <div class="card-footer">
            <button @click="submited = true" class="btn-submit">Submit</button>
          </div>
        </div>
      </div>
    </div>
    <div v-else>
      <div class="card-header text-center">
        <div class="card-img">
          <img src="../assets/illustration-thank-you.svg" alt="Mi SVG feliz" />
        </div>
        <div class="ronded-circle"><p>You selected {{ rate }} out of 5</p></div>
        <h2 class="title">Thank you!</h2>
      </div>
      <div class="card-body text-center">
        <p class="description">We appreciate you taking the time to give a rating. If you ever need more support,
        don’t hesitate to get in touch!</p>
      </div>
    </div>
  </div>
</template>
<script setup>
import { ref } from 'vue'
const rate = ref(0)
const b = ref([1, 2, 3, 4, 5])
const submited = ref(false)

</script>
<style scoped>

</style>
