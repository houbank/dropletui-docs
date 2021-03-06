# switch

## Attributes

| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| v-model |  | boolean |  |  |
| disabled | 不可选 | boolean |  |  |
| checkedColor | 选中状态的颜色 | string |  | \#027FF3 |

## slot

| name | 说明 |
| :--- | :--- |


## event

| 事件名 | 说明 | 回调参数 |
| :--- | :--- | :--- |
| wxChange |  | true false |

## Usage

```
<template>
    <div class="wx-demo">
        <wx-cell 
            text="有无住房"
            width="690px"
            height="140px"
            textColor="#333"
            textFontSize="32px"
            :hasArrow="false"
            @wxClick="handleClick">
                <wx-switch 
                    slot="right"
                    class="switch" 
                    v-model="value1" 
                    @wxChange="handleChange" 
                    :disabled="false">
                </wx-switch>
        </wx-cell>
        <wx-cell 
            text="有公积金"
            width="690px"
            height="120px"
            textColor="#333"
            textFontSize="32px"
            :hasArrow="false"
            @wxClick="handleClick">
                <wx-switch 
                    slot="right"
                    class="switch" 
                    v-model="value2" 
                    @wxChange="handleChange" 
                    :disabled="false">
                </wx-switch>
        </wx-cell>

        <div style="padding-top: 30px">
            <text class="wx-text">有公积金：{{ value1 }}</text>
            <text class="wx-text">有无住房：{{ value2 }}</text>
        </div>
    </div>
</template>

<style type="text/css">
    .wx-demo {
        align-items: center;
    }
    .wx-text {
        font-size: 32px;
    }
</style>

<script>
    import { WxSwitch, WxCell } from '../../index';

    export default {
        data () {
            return {
                value1: false,
                value2: true,
            }
        },

        methods: {
            handleChange (checked) {

            },
            handleClick (checked) {

            },
        },

        components: {
            WxSwitch,
            WxCell
        }
    }
</script>
```



