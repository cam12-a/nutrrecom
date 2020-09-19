
<template>
    <div class="Header">
        <nav class="banner">
       <!-- <ul class="ulbanner">
            <li><img src="" alt="logo" class="logo" v-bind:title="'Логотип приложения'"></li>
            <li class="main">Главная</li>
            <li class="menu">Создать меню</li>
            <li class="aboutUS">О нас</li>
            <li class="myAccount">Личный кабинет</li>
        </ul> -->
        <div class="textonRightOfLogo">
            <a href="#"><img src="../assets/logoNutr.png" alt="error" style="width:100px;height:70px"></a>
        </div>
       
        
        <ul>
            <input type="search" name="search" id="search">
            <li v-for="item in navList" v-bind:key="item" >
                <template v-if="item.children"  >
                    <a :href="item.url" :title="item.name" class="menu"  :class="{active}" @mouseover="isOpen=!isOpen ,active=!active">
                        {{item.name}}<svg viewBox="0 0 451.847 451.847" width="12"><path d="M225.923,354.706c-8.098,0-16.195-3.092-22.369-9.263L9.27,151.157c-12.359-12.359-12.359-32.397,0-44.751
        c12.354-12.354,32.388-12.354,44.748,0l171.905,171.915l171.906-171.909c12.359-12.354,32.391-12.354,44.744,0
        c12.365,12.354,12.365,32.392,0,44.751L248.292,345.449C242.115,351.621,234.018,354.706,225.923,354.706z" fill="#fff"/></svg>
                    </a>
                    <div :class="{isOpen}" class="dropdown">
                        <ul>
                            <li v-for="{url,name,index} in item.children" :key='index'>
                                <a :href="url" :title="name">{{name}}</a>
                            </li>

                        </ul>
                    </div>
                </template>
                <template v-else>
                    <a :href="item.url" :title="item.name">{{item.name}}</a>
                </template>
            </li>
          
        </ul>
        </nav>
        
    </div>
</template>
<script>
export default {
    name: 'Header',
    props:["item"],
    data(){
        return {
            isOpen:false,
            active:false,
            navList:[
                {url:"#",name:"Главная"},
                {url:"#",name:"Создать меню",children:[
                    {url:"www.facebook.com",name:"Молочные продукты"},
                    {url:"#",name:"Овощи"},
                    {url:"#",name:"Мясо"}

                ]},
                {url:"#",name:"О нас"},
                {url:"#",name:"Личный кабинет"}

            ]
        };

    }
    
}
</script>
<style scope>

.Header
{
 width: auto;
 height: 10%;
 display: grid;
  
}
.Header > nav > ul >li >a {
  background-color: rgba(255, 255, 255, 0.8);
  text-align: center;
}
nav
{
    background-color: white;
    
}
nav ul li {
    display: inline-table;
    margin-left: 10px;
}
.Header > nav > ul >li >a:hover {
 color: black;
}
.logo{
    margin-left: 500px;
}
.Header >nav  {
  grid-column: 1 / 6;
}
nav ul li.logo a{
    border: 0px solid white;
    padding: 0px 0px;
    position: relative;
    z-index: 1;
}

.textonRightOfLogo{
    position: absolute;
}
nav ul {
    margin-left: 25em;
    margin-top: 12px;
   
}
#search {
    width: 300px;
  border: 2px solid silver;
  font-size: 10pt;
  float: left;
  color: #63717f;
  padding-left: 45px;
  -webkit-border-radius: 5px;
  -moz-border-radius: 5px;
  border-radius: 10px;
}
</style>