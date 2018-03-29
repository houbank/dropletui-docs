# checkbox

## Attributes

| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| defualtChecked | 默认是否选中 | boolean |  | false |
| disabled |  | boolean |  | false |
| text | 文字 | string |  |  |
| align | 文字位置 | string |  | left |
| checkedColor | 选中复选框颜色 | string |  | \#027FF3 |

## slot

| name | 说明 |
| :--- | :--- |


## event

| 事件名 | 说明 | 回调参数 |
| :--- | :--- | :--- |
| wxChange |  | true or false |

## Usage

```
<template>
    <div class="wx-demo" style="margin-top:100px;margin-left:100px;">
        <wx-checkbox 
            text="我已阅读《xxx》" 
            v-model="checked"
            checkedColor="#027FF3"
            :defaultChecked="checked"
            align="left"
            :disabled="false"
            @wxChange="handleChange">
        </wx-checkbox>
        <text>value：{{ checked }}</text>
    </div>
</template>
<script>
    import { WxCheckbox } from 'weex-droplet-ui';
    const modal = weex.requireModule('modal');
    export default {
        components: {
            WxCheckbox,
        },
        data () {
            return {
                 checked: false,
                 wxchange: false,
            }
        },
        created () {

        },
        methods: {
            handleChange (checked) {
                console.log(checked)
            },
        }
    }
</script>

```



