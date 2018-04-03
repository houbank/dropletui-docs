# scrollbar

## Attributes

| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| items | data | array |  | \[\] |
| height |  | string |  | 700px |
| itemWidth |  | string |  | 250px |
| itemHeight |  | string |  | 100px |
| scrollDirection | 水平、垂直方向 | string | vertical、horizontal | vertical |

## slot

| name | 说明 |
| :--- | :--- |


## event

| 事件名 | 说明 | 回调参数 |
| :--- | :--- | :--- |
| wxChange |  | item data |

## Usage

```
<template>
    <div class="wx-demo">
        <wx-scrollerbar 
            :items="items"
            height="700px"
            @wxChange="handleChange"
            itemWidth="250px" 
            itemHeight="100px">
        </wx-scrollerbar>

        <div style="margin-top: 100px;"></div>

        <wx-scrollerbar 
            scrollDirection="horizontal"
            :items="items"
            height="100px"
            @wxChange="handleChange"
            itemWidth="150px" 
            itemHeight="100px">
        </wx-scrollerbar>
    </div>
</template>
<script>
    import { WxScrollerbar } from 'weex-droplet-ui';
    export default {
        components: {
            WxScrollerbar,
        },
        data () {
            return {
                items: ['demo1', 'demo2', 'demo3', 'demo4', 'demo5', 'demo6','demo7', 'demo8', 'demo9', 'demo10', 'demo11', 'demo12','demo13'],
            }
        },
        methods: {
            /**
             * 点击回调
             * @param  {[type]} item 被选中的项
             */
            handleChange (item) {
                console.log(item)
            }
        }
    }
</script>
<style scoped>
    
</style>

```



