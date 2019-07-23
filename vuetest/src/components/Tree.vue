<template>
    <ul class="clear-default">
        <li v-for="(item,index) in list " :key="index" class="lisi">
            <p @click="chooseFather(index)">{{item.content}}</p>
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
                console.log(v,o)
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
            this.showCurrent.push[false];
        })
        console.log(this.showCurrent);
    },
    created() {
       
    },
    methods:{
        
        chooseFather(index){
            console.log(index);
            this.showCurrent[index] = !this.showCurrent[index];
            console.log(this.showCurrent);
            // this.$nextTick(()=>{
            //     this.showCurrent[index] = !this.showCurrent[index];
            // })
            // 这样用是不合理的，用到了强制更新视图，我们上面改变的数据并没有
            this.$forceUpdate()
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
