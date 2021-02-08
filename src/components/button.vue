<template>
  <button @click="$emit('click', $event)">{{ text }}</button>
</template>

<script>
export default {
  name: "mybutton",
  props: {
    text: String
  }
};
</script>

<style scoped>
button {
  background: #ff7e00;
  border: 2px solid #ff7e00;
  box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.25);
  border-radius: 60px;
  font-weight: bold;
  font-size: 16px;
  padding: 15px 25px;
  outline: none;
}
@media (max-width: 1023px){
  button{
    font-size: 13px;
  }
}
button:focus {
  background: #343434;
  border: 2px solid #ff7e00;
  box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.25);
  border-radius: 60px;
  color: #ff7e00;
}
button:hover {
  background: #343434;
  border: 2px solid #ff7e00;
  box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.25);
  border-radius: 60px;
  color: #ff7e00;
}
</style>
