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
    <div class="wx-button" @click="handleClick" :style="buttonStyles">
        <text class="wx-text" :style="textStyles">
            <slot></slot>
        </text>
    </div>
</template>
<style>
    .wx-button {
        background-color: #4676FF;
        align-items: center;
        justify-content: center;
    }
    .wx-text {
        color: #ffffff;
        font-size: 32px;
    }
</style>
<script type="text/javascript">
    export default {
        props: {
            width: {
                type: String,
                default: '670px'
            },
            height: {
                type: String,
                default: '90px'
            },
            borderRadius: {
                type: String,
                default: '12px'
            },
            disabled: {
                type: Boolean,
                default: false
            },
            styles: {
                type: Object,
                default: function () {
                    return {}
                }
            },
            textColor: {
                type: String,
                default: '#ffffff'
            },
            textFontSize: {
                type: String,
                default: '36px'
            }
        },
        data () {
            return {
                buttonStyles: {},
                textStyles: {},
            }
        },
        created () {
             this.setStyle();
        },
        watch: {
          'disabled': function () {
              if(this.disabled){
                  this.buttonStyles['background-color'] = 'rgba(0, 0, 0, 0.1)'
              }else{
                  this.buttonStyles['background-color'] = '#4676FF'
              }
          }
        },
        methods: {
            setStyle () {
                const baseCss = {
                    height: this.height,
                    width: this.width,
                    'border-radius': this.borderRadius,
                };
                let style = Object.assign({}, baseCss, this.styles);
                this.buttonStyles = style;
                if(this.disabled){
                    this.buttonStyles['background-color'] = 'rgba(0, 0, 0, 0.1)'
                }
                this.textStyles = {
                    color: this.textColor,
                    fontSize: this.textFontSize
                };
            },

            handleClick (e) {
                if (this.disabled) return;
                this.$emit('wxClick', e);
            },
        }
    }
</script>
```



