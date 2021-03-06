# input 说明文档

## Attributes

| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| v-model |  |  |  |  |
| width | 100px | string |  | 无 |
| type | 类型 | string | text,number | text |
| icon | 前缀图标URL | string |  |  |
| tail | 尾部图标URL | string |  |  |
| placeholder | placeholder | string |  | 无 |
| value | value | string |  |  |
| disabled | disabled | boolean |  |  |
| autofocus | autofocus | boolean |  |  |
| maxlength | maxlength | string |  |  |
| iconStyle | 前缀图标样式 | object | 常规style样式 | 无 |
| tailStyle | 尾部图标样式 | object | 常规style样式 | 无 |

## slot

| name | 说明 |
| :--- | :--- |
| left | 左侧slot |

## event

| 事件名 | 说明 | 回调参数 |
| :--- | :--- | :--- |
| wxInput | input事件，回调无返回Event对象 | input value |
| wxBlur | 失去焦点 |  |
| wxFocus | 聚焦 |  |

## Usage

```
<template>
    <div>
        <wx-input 
            class="demo"
            placeholder="请输入手机号">
            <wx-icon class="icon" slot="left" name="search"></wx-icon>
        </wx-input>                
        <wx-input 
            class="demo"
            width="500px"
            type="password"
            placeholder="请输入密码">
            <wx-icon class="icon" slot="left" name="search"></wx-icon>
        </wx-input>
    </div>
</template>
<style scope>
    .demo {
        margin-top: 52px;
        margin-left: 40px;
        margin-right: 40px;
    }
    .icon {
        font-size: 44px;
        color:#DEDEDE;
        width: 100px;
        height: 100px;
        text-align: center;
        line-height: 100px;
    }
</style>
<script>
    import { WxInput, WxIcon } from 'weex-droplet-ui';
    export default {
        data () {
            return {
            }
        },
        components: { WxInput, WxIcon }
    }
</script>
```



