# loading

## Attributes

| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| visible | 是否显示 | Boolean |  | false |
| top | 相对于视窗的top | string | px值 | 无 |
| opacity | 背景透明度 | string | 0-1 |  |
| url | 菊花图片链接 | string |  | 有默认图片链接 |

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
        <wx-button @wxClick="openLoading">打开Loading</wx-button>
        <wx-loading opacity="0.6" :visible="visible" top="0px"></wx-loading>
    </div>
</template>

<script>
    import {WxLoading, WxButton} from 'weex-droplet-ui';

    export default {
        data () {
            return {
                visible: false
            }
        },
        components: {WxLoading, WxButton},
        methods: {
            openLoading () {
                this.visible = true
                setTimeout(() => {
                    this.visible = false
                }, 2000)
            }
        }
    }
</script>
```



