<template>
  <div class="Output">
    <h2>{{translatedText}}</h2>
  </div>
</template>

<script>
export default {
  name: 'Output',
  props:[
    'translatedText'
  ]
  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.Output{
  width:600px;
  height:70px;
  background-color: #eee;
  border:1px #ccc solid;
  border-radius: 10px;
  margin-left:370px;
  margin-top:15px;
}
.Output h2{
   line-height: 70px;
  text-align: center;
  font-size: 20px;
  color:#000000;
}
</style>
