<template>
    <div class="app">
        <div class="text">
          <ttext v-bind:string="text" v-bind:style = "style"></ttext>
        </div>
        <div class="op">
            <div class="choice">

              <!-- 颜色 -->
              <div class="color">
                <div class="option">
                  <div class="pink" v-on:click = "setColor('pink')">
                    粉色
                  </div>
                  <div class="skyblue" v-on:click="setColor('skyblue')">
                    蓝色
                  </div>
                  <div class="green" v-on:click="setColor('greenyellow')">
                    绿色
                  </div>
                  <div class="yellow" v-on:click="setColor('palegoldenrod')">
                    黄色
                  </div>
                  <div class="red" v-on:click="setColor('red')">
                    红色
                  </div>
                  <div class="black" v-on:click="setColor('black')">
                    复原
                  </div>
                </div>
              </div>
              <!-- 字体样式 -->
              <div class="yangshi">
                <div class="option">
                  <div class="weiruanyahei" v-on:click = "setFamily('微软雅黑')">
                    微雅
                  </div>
                  <div class="songti" v-on:click = "setFamily('宋体')">
                    宋体
                  </div>
                  <div class="heiti" v-on:click= "setFamilt('黑体')">
                    黑体
                  </div>
                  <div class="fangzheng" v-on:click = "setFamily('方正姚体')">
                    姚体
                  </div>
                  <div class="kaiti" v-on:click = "setFamily('楷体')">
                    楷体
                  </div>
                </div>
              </div>
              <!-- 保存或清空 -->
              <div class="function">
                <div class="option">
                  <a class="save" v-bind:href="'data:text/json;charset=utf-8,'+JSON.stringify(text)" download="myPage.txt">
                    保存
                  </a>
                  <div class="clear" v-on:click="clear">
                    清空
                  </div>
                </div>
              </div>

            </div>
            <div class="edit">
              <write v-on:hh = "change" ></write>
            </div>
        </div>
    </div>
</template>

<style>
    * {
  margin: 0;
  padding: 0; }

.app {
  height: 10000px;
  background-color: skyblue;
  display: flex;
  flex-direction: row; }
  .app .text {
    font-size: 18px;
    color: beige;
    height: 100%;
    flex: 2.5;
    background-color: #4b685e; }
  .app .op {
    height: 100%;
    flex: 1;
    background-color: black; }
    .app .op .choice {
      position: fixed;
      z-index: 1;
      width: 100%;
      background-color: aqua;
      height: 497px; }
    .app .op .edit {
      position: fixed;
      z-index: 100;
      top: 497px;
      width: 100%;
      background-color: pink;
      height: 300px; }
      .app .op .choice .color{
        padding-top: 10px;
        height: 143px;
        width: 100%;
        background-color: aqua;
        margin-bottom: 20px;
      }
      .app .op .choice .yangshi{
        padding-top: 10px;
        height: 143px;
        width: 100%;
        background-color: green;
        margin-bottom: 20px;
      }
      .app .op .choice .function{
        padding-top: 10px;
        height: 143px;
        width: 100%;
        background-color: aqua;
      }
      .app .op .choice .color .pink{
        display: inline-block;
        border-radius: 50%;
        width: 50px;
        height: 50px;
        background-color: white;
        text-align: center;
        line-height: 50px;
        margin-left: 10px;
        margin-top: 30px;
        transition: background-color .5s linear;
      }
      .app .op .choice .color .pink:hover{
        background-color: pink;
        box-shadow: 4px 4px 3px black;
      }
      .app .op .choice .color .skyblue{
        display: inline-block;
        border-radius: 50%;
        width: 50px;
        height: 50px;
        background-color: white;
        text-align: center;
        line-height: 50px;
        margin-left: 10px;
        margin-top: 30px;
        transition: background-color .5s linear;
        margin-left: 20px;
      }
      .app .op .choice .color .skyblue:hover{
        background-color: skyblue;
        box-shadow: 4px 4px 3px black;
      }
      .app .op .choice .color .green{
        display: inline-block;
        border-radius: 50%;
        width: 50px;
        height: 50px;
        background-color: white;
        text-align: center;
        line-height: 50px;
        margin-left: 10px;
        margin-top: 30px;
        transition: background-color .5s linear;
        margin-left: 20px;
      }
      .app .op .choice .color .green:hover{
        background-color: greenyellow;
        box-shadow: 4px 4px 3px black;
      }
      .app .op .choice .color .yellow{
        display: inline-block;
        border-radius: 50%;
        width: 50px;
        height: 50px;
        background-color: white;
        text-align: center;
        line-height: 50px;
        margin-left: 10px;
        margin-top: 30px;
        transition: background-color .5s linear;
        margin-left: 20px;
      }
      .app .op .choice .color .yellow:hover{
        background-color: palegoldenrod;
        box-shadow: 4px 4px 3px black;
      }
      .app .op .choice .color .red{
        display: inline-block;
        border-radius: 50%;
        width: 50px;
        height: 50px;
        background-color: white;
        text-align: center;
        line-height: 50px;
        margin-left: 10px;
        margin-top: 30px;
        transition: background-color .5s linear;
        margin-left: 20px;
      }
      .app .op .choice .color .red:hover{
        background-color: rgb(246, 69, 69);
        box-shadow: 4px 4px 3px black;
      }
      .app .op .choice .color .black{
        border-radius: 20%;
        width: 70px;
        height: 50px;
        background-color: white;
        text-align: center;
        line-height: 50px;
        transition: background-color .5s linear;
        margin-left: 145px;
        margin-top: 8px;
        border: 2px solid black;
      }
      .app .op .choice .color .black:hover{
        background-color: gray;
        box-shadow: 4px 4px 3px black;
      }
      .app .op .choice .yangshi .weiruanyahei{
        display: inline-block;
        border-radius: 50%;
        width: 50px;
        height: 50px;
        background-color: white;
        text-align: center;
        line-height: 50px;
        margin-left: 10px;
        margin-top: 30px;
        transition: background-color .5s linear;
        margin-left: 20px;
        font-family: '微软雅黑';
      }
      .app .op .choice .yangshi .weiruanyahei:hover{
        background-color: rgb(123, 111, 172);
        box-shadow: 4px 4px 3px black;
      }
      .app .op .choice .yangshi .songti{
        display: inline-block;
        border-radius: 50%;
        width: 50px;
        height: 50px;
        background-color: white;
        text-align: center;
        line-height: 50px;
        margin-left: 10px;
        margin-top: 30px;
        transition: background-color .5s linear;
        margin-left: 20px;
        font-family: '宋体';
      }
      .app .op .choice .yangshi .songti:hover{
        background-color: rgb(123, 111, 172);
        box-shadow: 4px 4px 3px black;
      }
      .app .op .choice .yangshi .heiti{
        display: inline-block;
        border-radius: 50%;
        width: 50px;
        height: 50px;
        background-color: white;
        text-align: center;
        line-height: 50px;
        margin-left: 10px;
        margin-top: 30px;
        transition: background-color .5s linear;
        margin-left: 20px;
        font-family: '黑体';
      }
      .app .op .choice .yangshi .heiti:hover{
        background-color: rgb(123, 111, 172);
        box-shadow: 4px 4px 3px black;
      }
      .app .op .choice .yangshi .fangzheng{
        display: inline-block;
        border-radius: 50%;
        width: 50px;
        height: 50px;
        background-color: white;
        text-align: center;
        line-height: 50px;
        margin-left: 10px;
        margin-top: 30px;
        transition: background-color .5s linear;
        margin-left: 20px;
        font-family: '方正姚体';
      }
      .app .op .choice .yangshi .fangzheng:hover{
        background-color: rgb(123, 111, 172);
        box-shadow: 4px 4px 3px black;
      }
      .app .op .choice .yangshi .kaiti{
        display: inline-block;
        border-radius: 50%;
        width: 50px;
        height: 50px;
        background-color: white;
        text-align: center;
        line-height: 50px;
        margin-left: 10px;
        margin-top: 30px;
        transition: background-color .5s linear;
        margin-left: 20px;
        font-family: '楷体';
      }
      .app .op .choice .yangshi .kaiti:hover{
        background-color: rgb(123, 111, 172);
        box-shadow: 4px 4px 3px black;
      }
      .app .op .choice .function .save{
        display:block;
        border-radius: 20%;
        width: 70px;
        height: 50px;
        background-color: white;
        text-align: center;
        line-height: 50px;
        transition: background-color .5s linear;
        margin-left: 145px;
        margin-top: 8px;
        border: 2px solid black;
      }
      .app .op .choice .function .save:hover{
        background-color: rgb(84, 155, 199);
        box-shadow: 4px 4px 3px black;
      }
      .app .op .choice .function .save:active{
        background-color: rgb(5, 36, 55);
        box-shadow: 4px 4px 3px black;
      }
      .app .op .choice .function .clear{
        border-radius: 20%;
        width: 70px;
        height: 50px;
        background-color: white;
        text-align: center;
        line-height: 50px;
        transition: background-color .5s linear;
        margin-left: 145px;
        margin-top: 8px;
        border: 2px solid black;
      }
      .app .op .choice .function .clear:hover{
        background-color: rgb(84, 155, 199);
        box-shadow: 4px 4px 3px black;
      }
      .app .op .choice .function .clear:active{
        background-color: rgb(5, 36, 55);
        box-shadow: 4px 4px 3px black;
      }

</style>

<script>
import ttext from './showText.vue'
import write from './writeText.vue'


export default{

  components:{
    ttext:ttext,
    write:write,  },
  methods:{
    change:function(val){
      this.text = val;
    },
    setFamily:function(val){
      this.fontFamily = val;
    },
    setColor:function(val){
      this.color = val;
    },
    clear:function(){
      this.text = '';
    }
  },
  data:function(){
    return {
      text:'',
      fontFamily:'',
      color:'',
    }
  },
  computed:{
    style:function(){
      return "color:" + this.color +";font-family:" + this.fontFamily +";"
    }
  }
    
}
</script>