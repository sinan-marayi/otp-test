<template>
  <div class="center-box">
    

      <div class="input-box">
        <input
          type="text"
          placeholder="_"
          id="first"
          v-on:keyup="changeFocus($event, '', 'first', 'second')"
          class="input-square-box"
          maxlength="1"
        />
        <input
          type="text"
          placeholder="_"
          id="second"
          v-on:keyup="changeFocus($event, 'first', 'second', 'third')"
          class="input-square-box"
          maxlength="1"
        />
        <input
          type="text"
          placeholder="_"
          id="third"
          v-on:keyup="changeFocus($event, 'second', 'third', 'fourth')"
          class="input-square-box"
          maxlength="1"
        />
        <input
          type="text"
          placeholder="_"
          id="fourth"
          v-on:keyup="changeFocus($event, 'third', 'fourth', 'fifth')"
          class="input-square-box"
          maxlength="1"
        />
        <input
          type="text"
          placeholder="_"
          id="fifth"
          v-on:keyup="changeFocus($event, 'fourth', 'fifth', '')"
          class="input-square-box"
          maxlength="1"
        />
      </div>
    
    
    <button class="btn" :on-click="verify()">Verify</button>
  </div>
</template>

<script>
export default {
  name: "OTP",
  props: {
    msg: String,
  },
  data(){
    return{
      isverified:false
    }
  },
  mounted:{

  },
  methods: {
    changeFocus: function( e,prev, current, next) {
      let currentInput = document.getElementById(current);
      if (currentInput.value.length && next !== "") {
        document.getElementById(next).focus();
      }
      if (e.key === "Backspace" && prev !=='') {
        document.getElementById(prev).focus();
      }
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.center-box {
  margin: auto auto auto auto;
  width: 500px;
  height: 150px;
  background-color: rgb(255, 255, 231);
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: min-content;
  padding: 30px;
  border-radius: 5px;
  border: .5px gainsboro solid;
}
.btn {
  color: white;
  background-color: rgb(231, 20, 119);
  opacity: 0.8;
  border: 0;
  border-radius: 5px;
  padding: 10px;
  font-size: 1rem;
  font-family: "Lucida Sans", "Lucida Sans Regular", "Lucida Grande",
    "Lucida Sans Unicode", Geneva, Verdana, sans-serif;
}
.btn:hover{
  opacity: 1;
}
.input-box {
  display: flex;
  width: 100%;
  align-items: center;
  justify-content: center;
  height: 60%;
  gap: 10px;
}
.input-square-box {
  width: 50px;
  height: 50px;
  border-radius: 5px;
  border: 1px gray solid;
  font-size: x-large;
  font-weight: 300;
  text-align: center;
outline: none;
}
.input-square-box::placeholder{
  opacity: 0.3;
}
</style>
