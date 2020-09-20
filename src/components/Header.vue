
<template>
    <div class="Header">
        <nav class="banner">
        <div class="textonRightOfLogo">
            <a href="#"><img src="../assets/logoNutr.png" alt="error" style="width:100px;height:70px"></a>
        </div>
    
    <ul class="menu">
          <input type="search" name="search" id="search">
    <li v-for="item in navList" v-bind:key="item" >
        <template v-if="item.name!='Создать меню'">
            <li>
                <a :href="item.url" :title="item.name">{{item.name}}</a>
            </li>
        </template>
        <template v-else>
            <li @mouseover="listOne = true" @mouseleave="listOne = false" >
                <a :href="item.url" :title="item.name" @mouseover="listOne = true" @mouseleave="listOne = false">{{item.name}}</a>
                    <template v-if="item.children" >
                        <transition name="fade">
                            <ul v-if="listOne" @click="listOne = false" class="mydropDown">
                                <li v-for="{url,name,index} in item.children" :key='index'>
                                    <a :href="url" :title="name" >{{name}}</a>
                                </li>
                            </ul>
                        </transition>
                </template>
            </li>
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
    data() {
    
        return {
            isOpen:false,
            active:false,
            listOne:   false,
           
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
    padding: 12px;
    height: 10px;
    
}
nav ul li {
    display: inline-table;
    margin-left: 10px;
    width: 80px;
}
.Header > nav > ul >li >a:hover {
 color: black;
 text-decoration:underline black;
 
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
    margin-left: 10em;
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
  margin-left: 22em;
}

</style>