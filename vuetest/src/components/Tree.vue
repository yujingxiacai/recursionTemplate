<template>
    <ul class="clear-default">
<<<<<<< HEAD
        <li v-for="(item,index) in list " :key="index" >
            <p class="lisi" @click="chooseFather(index)">{{item.content}}</p>
=======
        <li v-for="(item,index) in list " :key="index" class="lisi">
            <p @click="chooseFather(index)">{{item.content}}</p>
>>>>>>> a1c7ba246118b7e3c24433fd5026e5e99dd14d54
            <Tree v-if="showCurrent[index]" :list="item.child"/>
        </li>
    </ul>
    
</template>

<script>
export default {
    props:["list"],
    name:'Tree',
    data() {
        return {
            current: 0,
            showCurrent: [],
            cesi:[1,2,3,4]
        }
    },
    watch: {
        showCurrent:{
            handler(v,o){
<<<<<<< HEAD
                console.log("监听到了showCurrent的变化》》》",v,o);
=======
                console.log(v,o)
>>>>>>> a1c7ba246118b7e3c24433fd5026e5e99dd14d54
            },
            deep:true
        },
        current: {
            handler (v,o) {
                console.log(v,o);
            },
            deep:true
        }
    },
    mounted() {
        console.log(this.list);
        this.showCurrent = [];
        this.list.forEach((e,i)=>{
            this.showCurrent.push(false);
        })
        console.log(this.showCurrent);
    },
    created() {
       
    },
    methods:{
        
        chooseFather(index){
            // this.showCurrent[index] = !this.showCurrent[index];
            // 这样用是不合理的，用到了强制更新视图，我们上面改变的数据并没有及时更新，原因是因为vue不支持这样的修改
            // this.$forceUpdate()
            // 遇到这样的数据类型需要动态更新监听的话，只能是使用下面的方法，才能监听到。
            //  原因参照原文：https://cn.vuejs.org/v2/guide/list.html#%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A1%B9
            this.$set(this.showCurrent, index, !this.showCurrent[index]);         
        }
    },
}
</script>

<style scoped>
.clear-default{
    list-style: none;
    text-align: left;
    width: 100px;
}
.lisi{
    border-bottom: 1px solid #cccccc
}
</style>
