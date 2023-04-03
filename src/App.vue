<template>
  <div id="root">
    Hint Word : {{ word }}
    <form v-on:submit="onSubmitForm">
      <input type="text" v-model="inputValue" ref="answer">
      <button type="submit">input</button>
    </form>
  </div>
  <div> 
    {{ result }}
  </div>
</template>

<script>
export default {
  name: 'App',
  data(){
    return{
      word:'Word Vuelay',
      inputValue:'',
      result:'',
    }
  },
  methods:{
    onSubmitForm(e){
      e.preventDefault();
      if(this.word[this.word.length - 1] === this.inputValue[0]) {
        this.result = 'Correct Answer';
        this.word = this.inputValue;
        this.inputValue = '';
        this.$refs.answer.focus();
      } else {
        this.result = 'Wrong Answer';
        this.inputValue='';
      }
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

body {
  margin:0;
  padding:0;
}
</style>
