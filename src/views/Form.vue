<template>
  <form v-on:submit.prevent="submitForm" class="form">
    <h1 class="form-title">Form page</h1>
    <div class="cont">
      <label>Name</label>
      <input v-model="form.name" id="name" class="input" />
    </div>
    <div class="cont">
      <label>Email</label>
      <input v-model="form.email" id="email" class="input mail" />
    </div>
    <div class="cont">
      <label>Choose one:</label>
      <select v-model="form.sel" id="sel" class="sel">
        <option value="hola">hola</option>
        <option value="chao">chao</option>
      </select>
    </div>
    <div class="btn-wrapper">
      <button class="sub" type="submit">Send</button>
    </div>
  </form>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      form: {
        name: "",
        email: "",
        sel: "hola",
      },
    };
  },
  methods: {
    submitForm() {
      let formm = this.form;
      console.log("submitForm -> form", formm);
      axios
        .post("azure.server", formm)
        .then((res) => {
          console.log("submit;Form -> res", res);
          //Perform Success Action
        })
        .catch((error) => {
          console.log("submitForm -> error", error);
          // error.response.status Check status code
        })
        .finally(() => {
          //Perform action in always
        });
    },
  },
};
</script>

<style lang="scss">
.form {
  .form-title {
    text-align: center;
  }

  .cont {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin: 20px 0 0 0;
    label {
      font-size: 0.9;
    }
    .input {
      -webkit-appearance: none !important;
      background: #fff;
      padding: 5px;
      border-radius: 6px;
      border: 1px solid #ececec;
      height: 30px;
      outline: none;
      width: 200px;
      font-size: 14px;
    }
    .sel {
      background: #fff;
      padding: 5px;
      border-radius: 6px;
      border: 1px solid #ececec;
      outline: none;
      width: 200px;
      font-size: 14px;
      height: 40px;
    }
  }
  .btn-wrapper {
    text-align: center;
    margin: 30px 0 0 0;
    .sub {
      font-size: 14px;
      padding: 5px 10px;
      cursor: pointer;
      border-width: 0px;
      border-style: none;
      outline: none;
      background-color: #6581ff;
    }
    .sub:hover {
      background-color: #8ca0fc;
    }
  }
}
</style>
