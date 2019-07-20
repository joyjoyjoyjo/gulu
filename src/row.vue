<template>
    <div class="row" :style="{marginLeft:-gutter/2+'px', marginRight: -gutter/2-2+'px'}">
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
        created() {
            console.log(this.$children);
        },
        mounted() {
            console.log(this.$children);
            console.log(this.$children);
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