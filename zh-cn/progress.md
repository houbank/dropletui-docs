# progress

## Attributes

| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| percent | 进度的百分比 | number | 0-100 | 0 |
| width |  | string |  | 750px |
| height |  | string |  | 40px |
| animation | 是否有动画 | Boolean |  | true |
| innerStyle | 内部选中样式 | object |  | {} |
| outerStyle | 外部未选中样式 | object |  | {} |

## slot

| name | 说明 |
| :--- | :--- |


## event

| 事件名 | 说明 | 回调参数 |
| :--- | :--- | :--- |


## Usage

```
<template>
    <div>
        <wx-progress 
            :outerStyle="{'background-color': '#f5f5f5'}"
            :innerStyle="{'background-color': '#f5222d','border-top-right-radius': '40px','border-bottom-right-radius': '40px'}"
            class="progress" 
            :animation="true" 
            :percent="100">
        </wx-progress>
        <wx-progress 
            :outerStyle="{'background-color': '#f5f5f5'}"
            :innerStyle="{'background-color': '#1890ff','border-top-right-radius': '40px','border-bottom-right-radius': '40px'}"
            class="progress" 
            :animation="true" 
            :percent="90">
        </wx-progress>
        <wx-progress class="progress" :animation="true" :percent="80"></wx-progress>
        <wx-progress class="progress" :animation="true" :percent="70"></wx-progress>
        <wx-progress class="progress" :animation="true" :percent="60"></wx-progress>
    </div>
</template>

<script>
    import {WxProgress, WxButton} from 'weex-droplet-ui'

    export default {
        data () {
            return {
                
            }
        },
        components: {
            WxProgress,
            WxButton
        },
        methods: {
        }
    }
</script>
<style type="text/css" scoped>
    .progress {
        margin-top: 60px;
    }
</style>

```



