import { ref } from 'vue';

function UseDate(initialDate) {
  const date = ref(new Date(initialDate));

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
}

export default UseDate;
