<template>
    <div class="am-button-group">
        <slot></slot>
    </div>  
</template>

<script>
export default{
    mounted(){
        for(let node of this.$el.children){
            let name=node.nodeName.toLowerCase()
            if(name!=='button'){
                console.warn(`am-button-group的子元素应该全是am-button,但是你写的hi${name}`)
            }
        }
    }
}
    
</script>

<style lang="scss" scoped>
.am-button-group{
    display: inline-flex;
    vertical-align: middle;
      >.button {
        border-radius: 0;
        &:not(:first-child){
            margin-left: -1px;
        }
        &:first-child{
            border-top-left-radius: var(--border-radius);
            border-bottom-left-radius: var(--border-radius);
        };
        &:last-child{
            border-top-right-radius: var(--border-radius);
            border-top-left-radius: var(--border-radius);
        };
        &:hover{
            position: relative;
            z-index: 1;
        }
    }
}

</style>