# button 说明文档

## Attributes

| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| width |  | string |  | 670px |
| height |  | string |  | 90px |
| borderRadius |  | string |  | 12px |
| disabled |  | boolean | true\|false | false |
| styles | 常规css样式 | object |  | {} |
| textColor | 文本颜色 | string |  | \#fff |
| textFontSize | 字体大小 | string |  | 36px |

## slot

| name | 说明 |
| :--- | :--- |
| 空 | button内容 |

## Usage

```
<template>
    <div class="wx-demo">
        <wx-button 
          height="80px"
          width="450px"
          borderRadius="200px"
          textColor="#fff"
          textFontSize="32px"
          :disabled="disabled"
          @wxClick="wxClickHandle">测试1{{disabled}}</wx-button>

        <wx-button 
            height="80px"
            width="450px"
            borderRadius="200px"
            textColor="#fff"
            textFontSize="32px"
            :disabled="false"
            :styles="{'margin-left': '50px','margin-top': '80px'}"
            @wxClick="wxClickHandle">测试1</wx-button>
    </div>
</template>

<script>
    import { WxButton } from 'weex-droplet-ui';
    const modal = weex.requireModule('modal');
    export default {
        data(){
            return {
                disabled: true
            }
        },
      components: {
          WxButton 
      },
      mounted () {
          setTimeout(()=> {
              this.disabled = false
          },2000)
      },
      methods: {
          wxClickHandle () {
            modal.toast({
                message: 'clicked'
            })
          }
        }
    }
</script>
```



