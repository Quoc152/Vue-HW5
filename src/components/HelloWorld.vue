<script setup>
import { ref, computed } from 'vue';

const value = ref(0);

const isEven = computed(() => value.value % 2 === 0)

const decrement = () => {
  value.value--;
};

const increment = () => {
  value.value++;
};

</script>

<template>
  <div class="greetings">
    <div>        
      <label :class="isEven ? 'even' : 'odd'">
        {{ isEven ? 'Số chẵn' : 'Số lẻ' }}
      </label>
    </div>

    <div>
      <button @click="decrement">
      <font-awesome-icon :icon="['fas', 'minus']" />
    </button>
    <input type="number" v-model="value" />
    <button @click="increment">
      <font-awesome-icon :icon="['fas', 'plus']" />
    </button>
    </div>
  </div>
</template>

<style scoped>
.even {
  color: green;
  margin: 0 20px;
}

.odd {
  color: yellow;
  margin: 0 20px;
}

h1 {
  font-weight: 500;
  font-size: 2.6rem;
  position: relative;
  top: -10px;
}

h3 {
  font-size: 1.2rem;
}

input {
  height: 30px;
  font-size: 15px;
}

button {
  width: 50px;
  height: 30px;
  margin: 0 10px;
}

.greetings {
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>
