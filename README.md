### Vue-Wangeditor

本组件是针对wangeditor在vue2.0上封装的组件，为方便使用vue2.0的开发者封装。

### Usage

```
npm install --save vue-wangeditor
```

在项目中直接引入即可：

```
<template>
  <vue-wangeditor id="editor" v-model="text></vue-wangeditor>
</template>

import vueWangeditor from 'vue-wangeditor'
export default {
  ...
  components: {
    vueWangeditor
  }
}
```

### 配置说明

#### Menus
菜单数组：

```
[
        'source',	// 源码模式
        '|',
        'bold',	// 粗体
        'underline',	// 下划线
        'italic',	// 斜体
        'strikethrough',	// 中线
        'eraser',	// 清空格式
        'forecolor',	// 文字颜色
        'bgcolor',	// 背景颜色
        '|',
        'quote',	// 引用
        'fontfamily',	// 字体
        'fontsize',	// 字号
        'head',	// 标题
        'unorderlist',	// 无序列表
        'orderlist',	// 有序列表
        'alignleft',	// 左对齐
        'aligncenter',	// 居中
        'alignright',	// 右对齐
        '|',
        'link',	// 链接
        'unlink',	// 取消链接
        'table',	// 表格
        'emotion',	// 表情
        '|',
        'img',	// 图片
        'video',	// 视频
        'location',	// 位置
        'insertcode',	// 插入代码
        '|',
        'undo',	// 撤销
        'redo',	// 重做
        'fullscreen'	// 全屏
    ];

```

#### Code Types

代码类型：

```
apache/bash/coffeescript/cpp/cs/css/diff/http/ini/java/javascript/json/makefile/html/markdown/nginx/objectivec/perl/php/python/ruby/sql
``` 

#### Attribute

| 参数        | 说明   |  类型  |  可选值  | 默认值 |
| --------   | :-----:  | :----:  | -------- | -------- |
| id      | 创建编辑器的唯一标识   |    String  |  无 |  无 |
| value      | 富文本编辑器绑定的内容   |    String  |  无 |  无 |
| width      | 富文本编辑器宽度   |    String  |  无 |  600 |
| height      | 富文本编辑器高度   |    String  |  无 |  400 |
| uploadImgUrl      | 图片上传地址   |    String  |  无 |  无 |
| uploadParams      | 图片上传附带参数   |    String  |  无 |  无 |
| uploadHeader      | 图片上传附带头部   |    String  |  无 |  无 |
| pasteFilter      | 是否开启粘贴样式过滤   |    boolean  |  true/false |  false |
| mapKey      | 百度地图key   |    String  |  无 |  无 |
| menus      | 编辑器菜单   |    String  |  无 |  全部 |
| disabledMenus      | 禁用菜单（优先级在menus后）   |    String  |  无 |  无 |
| codeDefaultLang      | 默认插入代码类型   |    String  |  参照上方代码类型|  javascript |
| hideLinkImg      | 是否隐藏添加网络图片功能（需配置uploadImgUrl方可生效）   |    String  |  true/false |  false |
| menuFixed      | 是否开启菜单栏吸顶   |    String  |  true/false |  true |
| disabled      | 是否禁用编辑器   |    boolean  |  true/false |  true |
| isRealtime      | 是否实时对绑定值进行更新   |    boolean  |  true/fasle |false |  true |
| jsFilter      | 是否过滤js代码   |    boolean  |  true/false |  true |

#### Methods
| 方法名      | 说明   |  参数  |  返回值说明 | 返回值类型 |
| --------   | :-----:  | :----:  | -------- | -------- |
| getHtml   | 获取编辑器当前内容的html代码片段  |  无 | 内容的html代码片段 | String |
| getText   | 获取编辑器当前内容的文本格式  | 无  | 内容的纯文本 | String |
| insertImg   | 上传图片后手动插入图片  | url  | 无 | 无 |
| setHtml   | 设置编辑器内容  | text  | 无 | 无 |
| appendHtml   | 追加编辑器内容  | text  | 无 | 无 |
| clear   | 清空编辑器内容  | 无  | 无 | 无 |
| enable   | 启用编辑器  | 无  | 无 | 无 |
| disable   | 禁用编辑器  | 无  | 无 | 无 |
| destroy   | 销毁编辑器  | 无  | 无 | 无 |
| undestroy   | 恢复编辑器  | 无  | 无 | 无 |

#### Events
| 事件名        | 说明   |  参数  |  返回值说明 | 返回值类型 |
| --------   | :-----:  | :----:  | -------- | -------- |
| change   | 编辑器内容变化时触发的事件  | 无  | 无 | 无 |
| load   | 图片上传完成出发的事件  | originalName, resultText | originalName：文件原名resultText：返回的数据 | OriginalName：String resultText：String |
| timeout   | 图片上传超时触发的事件 | 无  | 无 | 无 |
| error   | 图片上传出错触发的事件  | 无  | 无 | 无 |



#### 版本更新

1.3.8
增加了insertImg方法，在上传图片后可自行处理图片url再插入编辑器中。