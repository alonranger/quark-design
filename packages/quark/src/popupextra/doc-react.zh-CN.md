# Popupextra

### 介绍

浮层

### 安装

```tsx
import { PopupExtra } from "@quarkd/quark-react";
```

### 基本使用

```js
export default () => {
  const [open, setOpen] = useState(false);

  const handleClose = () => setOpen(false);
  const handleOpen = () => setOpen(true);

  return (
    <div>
      <div
        onClick={handleOpen}
      >
        基本使用
      </div>
      <PopupExtra
        title="大标题文案"
        subtitle="副标题文案"
        onClosed={handleClose}
        open={open}
      >
        <div class="popup-body">
          <h4 class="">1.正正正正正正正正正正正</h4>
          <p>孫子曰：兵者，國之大事，死生之地，存亡之道。</p>
        </div>
      </PopupExtra>
    </div>
  );
};
```

### 自定义标题

通过设置 `slot='title'` 可以覆盖属性中的 `title`，从而实现自定义 `title`。

```js
<PopupExtra
  subtitle="副标题文案"
  open={open}
  onClosed={() => {
    open = false;
  }}
>
  <div slot="title">
    <span style="color: red">自定义</span>大标题文案
  </div>

  <div class="popup-body">
    <h4 class="">1.正正正正正正正正正正正</h4>
    <p>孫子曰：兵者，國之大事，死生之地，存亡之道，不可不察也。</p>
  </div>
</PopupExtra>
```

### 关闭浮层

设置 `closed` 方法

```js
<PopupExtra open={open} onClosed={() => { setOpen(false) } />
```

## API

### Props

| 参数      | 说明                     | 类型             | 默认值    |
| --------- | ------------------------ | ---------------- | --------- |
| open      | 弹窗状态                 | `boolean`        | `require` |
| title     | 主标题                   | `string`         |
| subtitle  | 主标题                   | `string`         |
| hideclose | 是否隐藏右上角关闭按钮   | `boolean `       | `false`   |
| round     | 是否圆角                 | `boolean `       | `true`    |
| safearea  | 是否开启底部安全区域适配 | `boolean`        | `false`   |
| zindex    | popup 层级设置           | `number、string` | -         |
| onClosed  | 组件关闭回调             | `（）=> void`    |

## 样式变量

组件提供了以下[CSS 变量](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Using_CSS_custom_properties)，可用于自定义样式，使用方法请参考[主题定制](#/zh-CN/guide/theme)。

| 名称                                 | 说明                     | 默认值                                        |
| ------------------------------------ | ------------------------ | --------------------------------------------- |
| `--popup-extra-title-color`          | 主标题颜色               | `#242729`                                     |
| `--popup-extra-subtitle-color`       | 副标题颜色               | `#879099`                                     |
| `--popup-extra-mask-color`           | 蒙层背景                 | `rgba(0, 0, 0, 0.7)`                          |
| `--popup-extra-z-index`              | 组件层级                 | `999`                                         |
| `--popup-extra-max-height`           | popup 内容区域最大高度   | `90%`                                         |
| `--popup-extra-min-height`           | popup 内容区域最小高度   | -                                             |
| `--popup-extra-border-radius`        | popup 圆角大小           | `16px`                                        |
| `--popup-extra-title-font-family`    | popup 主标题 font-family | `PingFangSC-Medium, PingFang SC, sans-serif`  |
| `--popup-extra-subtitle-font-family` | popup 副标题 font-family | `PingFangSC-Regular, PingFang SC, sans-serif` |
