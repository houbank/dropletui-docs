# radio 说明文档

## Attributes

| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| size | 大小 | string |  | 50px |
| align | 文本位置 | string | left、right | left |
| items | 数据格式参照demo | array |  | \[\] |
| checkedColor | 选中颜色 | string |  | \#027FF3 |
| textColor | 文本颜色 | string |  | \#4D4D4D |
| textFontSize | 文本大小 | string |  | 32pxslot |

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
        <wx-radio 
            checkedColor="#027FF3"
            size="50px"
            align="left"
            textColor="#4D4D4D"
            textFontSize="32px"
            :items="items"
            @wxChange="handleChange">
        </wx-radio>
        <text style="margin-top:100px;">{{ selected.label }}</text>
    </div>
</template>
<style type="text/css">
    .wx-demo {
        margin-top: 100px;
        margin-left: 100px;
    }
</style>
<script>
    import { WxRadio } from 'weex-droplet-ui';
    const modal = weex.requireModule('modal');
    export default {
        components: {
            WxRadio,
        },
        data () {
            return {
                 items: [
                    {label: '有公积金', value: '0', checked: true},
                    {label: '无公积金', value: '1', checked: false},
                 ],
                 selected: null,
            }
        },
        created () {
            this.selected = this.items[0]
        },
        methods: {
            handleChange (item) {
                this.selected = item;  
            },
        }
    }
</script>

```



