<template>
  <div class="translate row">
    <form v-on:submit="formSubmit" class="well form-inline col-md-6 col-md-offset-3" id="trans">
      <input type="text" placeholder="输入要翻译的内容" v-model="textToTranslate" class="form-control" style="margin-left:120px;">
      <select v-model="language" class="form-control">
        <option value="en">English</option>
        <option value="ru">Russian</option>
        <option value="ko">Korean</option>
        <option value="fr">French</option>
      </select>
      <input type="submit" value="翻译" class="btn btn-primary"/>
    </form>
  </div>
</template>

<script>
export default {
  name: 'translate',
  data () {
    return {
      textToTranslate:"",
      language:""
    }
  },
  methods:{
    formSubmit:function(e){
      this.$emit('formSub',this.textToTranslate,this.language);
      e.preventDefault();

    }
  },
  created:function(){
    this.language="en";
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.well{
  height:80px;
  background-color: #eee;
  /*width:600px;
  position: relative;*/
  margin-left: 345px;
}
#trans{
  border:1px #ccc solid;
  border-radius: 10px;
}
</style>
