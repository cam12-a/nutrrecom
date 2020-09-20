<template>
    <div class="container Body">
       <carousel>
          <template v-for="product in products" :key="product" >
                <div class="product row">
                    <slide>
                        <li class="productLi">
                            <a :href="'../'+product.name+'/'+product.id" :title="product.name">
                                <p>{{product.name}}</p>
                                <img :src="product.img" style="width:100px;height:70px">
                                <p>{{product.description}}</p>
                            </a>
                        </li>
                     </slide>
                </div> 
            </template> 
        </carousel>
    </div> 
</template>
<script>

export default {

    el:'.Body',
    props:['product'],
    data() {
       return {
        products:[
            {name:'Молоко', img:'../assets/logoNutr.png',description:'dsafsdgf',id:"14a"},
            {name:'Молоко', img:'../assets/logoNutr.png',description:'dsafsdgf',id:"14a"},
            {name:'Молоко', img:'../assets/logoNutr.png',description:'dsafsdgf',id:"14a"},

        ],
       };
        
    }
}
</script>
<style scoped>

.Body {
    height: 500px;
    margin-left: 50px;
    margin-right: 50px;
    margin-top: 50px;
    margin-bottom: 50px;
}
.product {
    border: 2px solid blanchedalmond;
    display: inline-block;
    top: 2em;
    margin-left: 10px;
    border-radius: 50%;
    width: 250px;
    height: 250px;
    margin-bottom: 10px;

}

.product li {
    list-style-type: none;
}
.productLi{
    margin-left: 28%;
    margin-right: 28%;
    margin-top: 10%;
     
}
</style>