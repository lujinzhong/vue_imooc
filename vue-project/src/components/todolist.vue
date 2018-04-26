<template>
  <div>
     <li @click='tough'>
        {{content}}
        </li>
  </div>
  
</template>

<script>
export default {
    props:['content','index'],
      methods:{
        tough:function(){
          //子组件向父组件传递消息
          this.$emit('delete',this.index)
          
        }
      }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
