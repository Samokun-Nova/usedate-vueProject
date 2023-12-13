<template>
  <div class="usedate-box">
  <div class="container">
    <p class="title" >{{ date }}</p>
    <button @click="addDays(1)" class="hover-btn">Add 1 Day</button>
    <button @click="addMonths(1)" class="hover-btn">Add 1 Month</button>
  </div>
</div>
</template>

<script>
import { ref } from 'vue';

export default {
  setup() {
    const date = ref(new Date());

    const addDays = (daysToAdd) => {
      const newDate = new Date(date.value);
      newDate.setDate(newDate.getDate() + daysToAdd);
      date.value = newDate;
    };

    const addMonths = (monthsToAdd) => {
      const newDate = new Date(date.value);
      newDate.setMonth(newDate.getMonth() + monthsToAdd);
      date.value = newDate;
    };

    return {
      date,
      addDays,
      addMonths,
    };
  },
};
</script>
<style>
button {
  width: 200px;
  height: 50px;
  font-size: 20px;
  border-radius: 10px;
  border: none;


}
.hover-btn {
  padding: 10px;
  cursor: pointer;
  transition: background-color 0.3s;
}

.hover-btn:hover {
  background-color: lightgray;
  width: 205px;
  height: 55px;
}
.title {
  font-size: 20px;
  color:rgb(56, 89, 209)

}
.button:hover {
  color: blue;
}
.usedate-box {
  color: blue;
  background-color: rgb(204, 224, 229);
  width: 600px;
  height: 250px;
  display: flex;
  justify-content: center;
  align-items: center;
  margin: 0 auto;
  border-radius: 10px;
  border: none;
  
  

}
.container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  margin: 0 auto;
  gap: 20px;

}
template {
  background-color:aqua;
}
</style>
