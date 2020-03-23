<template>
    <div class="tab-control">
        <div class="tab-control-item"
              v-for="(item,index) in titles"
              :key = index 
              :class="{active:currentId === index}"
              @click="itemClick(index)">
             <span>{{item}}</span>
         </div>
    </div>
</template>
<script>
export default {
    name: 'TabControl',
    props:{
        titles: {
            type:Array,
            default(){
                return []
            }
        }
    },
    data(){
        return {
            currentId: 0
        }
    },
    methods: {
        itemClick(index){
           this.currentId = index;
        }
    }
}
</script>
<style scoped>
    .tab-control {
        display: flex;
        height: 44px;
        line-height: 44px;
        text-align: center;
        font-size: 14px;
    }
    .tab-control-item {
        flex: 1;
        
    }
    .tab-control-item span {
        padding: 3px;
    }
    .active {
        color: var(--color-high-text);
    }
    .active span {
        border-bottom: 2px solid var(--color-tint);
    }
</style>
