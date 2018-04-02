# header

## Attributes

| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| hasBackIcon | 是否有回退箭头 | boolean |  | true |
| text | 文本内容 | string |  |  |
| hasBottom | 是否有bottom线 | boolean |  | true |
| useDefaultBack | 点击返回箭头是否使用this.$router.back | boolean |  | true |
| textColor |  | string |  | \#333333 |
| textFontSize | px值 | string |  | 44px |
| arrowColor |  | string |  | \#4676FF |
| arrowSize | px值 | string |  | 32px |

## slot

| name | 说明 |
| :--- | :--- |
| 默认slot |  |
| header-left |  |
| header-center |  |
| header-right |  |

## event

| 事件名 | 说明 | 回调参数 |
| :--- | :--- | :--- |
| wxBack | 如果不使用默认router，则可以回调 | 无 |

## Usage

```
<template>
    <div class="wx-demo">
        <wx-header textFontSize="40px" textColor="#333" arrowColor="#333" arrowSize="30px" :hasBottom="true" text="帮助" @wxBack="wxBackHandle"></wx-header>

         <wx-header text="帮助" @wxBack="wxBackHandle"></wx-header>
    </div>
</template>
<script>
    import { WxHeader } from 'weex-droplet-ui';
    const modal = weex.requireModule('modal');
    export default {
        components: {
            WxHeader
        },
        data () {
            return {

            }
        },
        created () {

        },
        methods: {
            wxBackHandle () {
                modal.toast({
                    message: 'back'
                })
            },
        }
    }
</script>

```



