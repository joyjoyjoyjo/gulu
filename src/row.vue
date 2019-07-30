<template>
    <div class="row" :style="rowStyle" :class="rowClass">
        <slot></slot>
    </div>
</template>
<script>
    export default {
        name : 'GuluRow',
        props : {
            gutter:{type:[Number,String]},
            align: {
                type: String,
                validator (value) { return ['left', 'right', 'center'].includes(value) }
            },
        },
        computed : {
            rowStyle(){
                let {gutter} = this;
                return {marginLeft:-gutter/2+'px', marginRight: -gutter/2-2+'px'}
            },
            rowClass() {
                let {align} = this;
                return [align && `align-${align}`];
            },
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
  .row {
    display: flex;
    &.align-left {
      justify-content: flex-start;
    }
    &.align-right {
      justify-content: flex-end;
    }
    &.align-center {
      justify-content: center;
    }
  }
</style>