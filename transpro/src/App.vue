<template>
  <div id="app">
    <h1>在线翻译</h1>
    <h5 class="text-muted">简单 / 易用 / 便捷</h5>
    <Translate v-on:formSub="translateText"></Translate>
    <Output v-bind:translatedText="translatedText"></Output>
  </div>
</template>

<script>
import Translate from './components/Translate'
import Output from './components/Output'

export default {
  name: 'App',
  data:function(){
      return{
        translatedText:""
      }
  },
  components: {
    Translate,Output
  },
  methods:{
    translateText:function(text,language){
      this.$http.get('https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20180305T143933Z.d87ffb49bbd9cb80.6a9c4cad5cd0e8251249146aca113cdd0b2ce7cb&lang='+language+'&text='+text)
      .then((response)=>{
        //console.log(response.body.text[0]);
        this.translatedText='Answer:'+response.body.text[0];
      })
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
