<template>
    <div class="row" :style="rowStyle">
        <slot></slot>
    </div>
</template>
<script>
    export default {
        name:'GuluRow',
        props:{
            gutter:{
                type:[Number,String]
            }
        },
        computed:{
            rowStyle(){
                let {gutter} = this;
                return {marginLeft:-gutter/2+'px', marginRight: -gutter/2-2+'px'}
            }
        },
        mounted() {
            this.$children.forEach((vm)=>{
                vm.gutter = this.gutter;
            })
        }
        // Vue父子之间的顺序
        // var div = document.createElement('div') //created
        // var childDiv = document.createElement('div') //created
        // div.appendChild(childDiv) //mounted
        // div.appendChild(div) //mounted
    }
</script>
<style scoped lang="scss">
    .row{
        display: flex;

    }
</style>