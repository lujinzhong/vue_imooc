<template>
  <!-- 要求用一个标签包住所有的模板，否则会报错 -->
  <div>
      <input v-model="value"/>
      <button @click="add">submit</button>
      <div>
        <ul>
         <list v-for="(item,index) of list" :key="index" :content="item"
          :index="index"  @delete="ondelete"></list>
        </ul>
      </div>
    </div>
</template>

<script>
//引入组件
import todolist from './components/todolist'

export default {
          components:{
            //引用组件别名
            'list':todolist

          },
          data(){
            return{
              value:"",
              list:[]
            }
          },
          methods:{
                add:function()
                {
                  this.list.push(this.value),
                  this.value=""
                },
               ondelete:function(index)
                {

                  this.list.splice(index)
                }
        }
  
}
</script>

<style>

</style>
