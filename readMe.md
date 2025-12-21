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

这个例子展示了如何使用Service Worker处理各种事件和API。

主要功能包括：

1. **Omnibox API**: 在地址栏中输入"api"关键字后可以快速搜索Chrome扩展API
   - 安装扩展后，默认会提供一些API建议如tabs、storage、scripting
   - 可以输入任意Chrome API名称直接跳转到相关文档页面
   - 历史搜索记录会被保存以便快速访问

2. **定时提示功能**:
   - 使用Alarms API定期从服务器获取Chrome扩展开发技巧
   - 每分钟更新一次提示内容
   - 在Chrome开发者文档网站上显示一个小部件，用户可以点击查看开发技巧

3. **Content Script**:
   - 在Chrome开发者文档网站(https://developer.chrome.google.cn/*)上注入脚本
   - 添加一个"Tip"按钮到页面导航栏
   - 点击按钮可查看从服务端获取的开发技巧

4. **权限说明**:
   - `storage`: 用于存储API搜索历史和提示内容
   - `alarms`: 用于定时更新提示内容

这个示例演示了现代Chrome扩展的核心概念：后台处理(Service Worker)、内容脚本注入、浏览器UI集成(Omnibox)以及多种Chrome APIs的组合使用。