# input 说明文档

### Input Attributes {#input-attributes}

| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| width | 宽 | string |  |  |
| type | 类型 | string |  | text |
| icon | 前缀图标url | string |  |  |
| tail | 尾部图标URL | string |  |  |
| placeholder | placeholder | string |  | 无 |
| value | value | string |  |  |
| disabled | disabled | boolean |  |  |
| autofocus | autofocus | boolean |  |  |
| maxlength | maxlength | string |  |  |
| iconStyle | 前缀图标样式 | object | 常规style样式 | 无 |
| tailStyle | 尾部图标样式 | object | 常规style样式 | 无 |
|  |  |  |  |  |

## slot

| name | 说明 |
| :--- | :--- |
| left | 左侧slot |

## event

| 事件名 | 说明 | 回到参数 |
| :--- | :--- | :--- |
| wxInput |  | input value |

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
    import WxInput from '../../packages/wx-input/index';
    import WxIcon from '../../packages/wx-icon/index';
    export default {
        data () {
            return {
            }
        },
        components: { WxInput, WxIcon }
    }
</script>
```



