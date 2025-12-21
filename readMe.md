# chrome 插件开发练习

## 第一个练习(hello)

1. 创建一个chrome插件
2. 创建一个manifest.json文件

## 第2个练习(run-in-every-page)

1. 创建一个chrome插件
   1. 创建一个manifest.json文件
   2. 创建一ge content-script.js文件

## 第3个练习(inject-into-active-tab)

1. 创建一个chrome插件
2. 创建一个manifest.json文件
3. 初始化扩展程序
   1. 扩展程序的service worker和web service worker不一样
   2. service worker是一个后台程序
   3. 是一种特殊的javascript运行环境，用于处理时间，并在不需要时候终止
   4. `runtime.OnInstalled()`方法允许扩展程序在安装时**设置初始状态**或**完成某些任务**，扩展程序可以通过`Storage API`和`IndexedDB`来存储应用状态
4. 启用扩展程序操作
   用于控制扩展程序的工具栏图标。**当用户选择扩展程序图标时，扩展程序会运行代码或现实弹出式窗口**

   *特别说明：* activeTab权限 授予扩展程序在有效标签页上执行代码的临时能力，允许访问当前标签页的敏感属性

   *触发权限的互动：* 1.键盘的快捷键组合；2.选择上下文菜单项；3接受地址栏中的建议；4.点击扩展程序图标

5. 跟踪当前标签页的状态
  
   用户点击扩展程序操作后，扩展程序会检查网址是否与文档页面匹配。接下来，它会检查当前标签页的状态并设置下一个状态。

## 使用service worker 处理事件(quick-api-reference)
