# range

## Attributes

| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| v-model |  | number |  |  |
| width |  | string |  | 750px |
| height |  |  |  | 10px |
| circleStyle | 圆圈style | object |  | {} |
| innerStyle | 未选中的部分style | object |  | {} |
| outerStyle | 被选中的范围style | object |  | {} |

## slot

| name | 说明 |
| :--- | :--- |


## event

| 事件名 | 说明 | 回调参数 |
| :--- | :--- | :--- |
| wxChange |  | 0-100值 |

## Usage

```
<template>
    <div class="wx-demo">
        <wx-range 
            ref="range"
            width="400px"
            :innerStyle="{'background-color': '#a9acb1'}"
            :outerStyle="{'background-color': '#1890ff'}"
            v-model="range"
            @wxChange="handleChange">
        </wx-range>
        <text style="margin-top:100px;font-size: 32px;">{{ range }}</text>
        <wx-button class="button" @wxClick="setRange()">设置进度50%</wx-button>
        
         <text style="margin-top:100px;"></text>
        <wx-range 
            width="450px"
            height="4px"
            v-model="range2"
            :circleStyle="{'background-color': '#f1f1f1', 'width': '50px', 'height': '50px'}"
            :innerStyle="{'background-color': '#f5222d'}"
            @wxChange="handleChange2">
        </wx-range>
        <text style="margin-top:100px;font-size: 32px;">{{ range2 }}</text>
    </div>
</template>
<style type="text/css">
    .wx-demo {
        padding-top: 100px;
        align-items: center;
        background-color: #fff;
    }
    .button {
        margin-top: 100px;
        margin-left: 50px;
    }
</style>
<script>
    import { WxRange, WxButton } from 'weex-droplet-ui';

    export default {
        components: {
            WxRange,
            WxButton
        },
        data () {
            return {
                range: 0,
                range2: 0,
            }
        },
        created () {

        },
        methods: {
            handleChange (range) {
                this.range = range;
            },

            handleChange2 (range2) {
                this.range2 = range2;
            },

            setRange () {
                this.$refs.range.setRange(50);
            },
        }
    }
</script>

```



