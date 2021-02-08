<template>
  <form action="#">
    <label for="name">Имя</label>
    <input type="text" id="name" />
    <label for="mail">E-mail</label>
    <input type="text" id="mail" />
    <label for="phone">Телефон</label>
    <input type="text" id="phone" />
    <div>
      <input type="checkbox" id="box" /><label for="box"
        >Даю согласие на обработку и хранение персональных данных</label
      >
    </div>
    <my-button text="Оставить заявку"></my-button>
  </form>
</template>

<script>
import myButton from "@/components/button";
export default {
  name: "myform",
  components: {
    myButton
  }
};
</script>

<style scoped>
form {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  font-weight: normal;
  font-size: 18px;
  line-height: 36px;
  color: #ffffff;
  margin: 50px 0;
  position: relative;
  width: 30%;
}
input {
  border: 1px solid white;
  background: none;
  padding: 15px 30px;
  width: 100%;
  outline: none;
  color: white;
  margin-bottom: 10px;
}
@media (max-width: 1023px) {
  form {
    max-width: 250px;
  }
}
#box {
  width: 20px;
}
div {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin: 20px 0;
}
label {
  font-weight: normal;
  font-size: 14px;
  line-height: 18px;
  color: #ffffff;
}
</style>
