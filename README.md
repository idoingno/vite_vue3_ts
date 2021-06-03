# Vue 3 + Typescript + Vite

#### 规范目录结构
```
├── publish/
└── src/
    ├── assets/ // 静态资源目录
    ├── common/ // 通用类库目录
    ├── components/ // 公共组件目录
    ├── router/ // 路由配置目录
    ├── store/ // 状态管理目录
    ├── style/ // 通用 CSS 目录
    ├── utils/ // 工具函数目录
    ├── views/ // 页面组件目录
    ├── App.vue
    ├── main.ts
    ├── shims-vue.d.ts
├── tests/ // 单元测试目录
├── index.html
├── tsconfig.json // TypeScript 配置文件
├── vite.config.ts // Vite 配置文件
└── package.json
```

#### 提交规范

> 如果 git commit 的描述信息精准，在后期维护和 Bug 处理时会变得有据可查，项目开发周期内还可以根据规范的提交信息快速生成开发日志，从而方便我们追踪项目和把控进度。

##### commit message 格式规范
commit message 由 Header、Body、Footer 组成。

###### Header
<type>(<scope>): <subject>  Header 部分包括三个字段 type（必需）、scope（可选）和 subject（必需）。

| 值 | 描述 |
| ------ | ------ |
| feat | 新增一个功能 |
| fix | 修复一个 Bug |
| docs | 文档变更 |
| style | 代码格式（不影响功能，例如空格、分号等格式修正） |
| refactor | 代码重构 |
| perf | 改善性能 |
| test | 测试 |
| build | 变更项目构建或外部依赖（例如 scopes: webpack、gulp、npm 等） |
| ci | 更改持续集成软件的配置文件和 package 中的 scripts 命令，例如 scopes: Travis, Circle 等 |
| chore | 变更构建流程或辅助工具 |
| revert | 代码回退 |

###### scope
scope 用于指定本次 commit 影响的范围。scope 依据项目而定，例如在业务项目中可以依据菜单或者功能模块划分，如果是组件库开发，则可以依据组件划分。（scope 可省略）

###### subject
subject 是本次 commit 的简洁描述，长度约定在 50 个字符以内，通常遵循以下几个规范：

用动词开头，第一人称现在时表述，例如：change 代替 changed 或 changes
第一个字母小写
结尾不加句号（.）

##### Body
body 是对本次 commit 的详细描述，可以分成多行。（body 可省略）

跟 subject 类似，用动词开头，body 应该说明修改的原因和更改前后的行为对比。

##### Footer
如果本次提交的代码是突破性的变更或关闭缺陷，则 Footer 必需，否则可以省略。

突破性的变更

当前代码与上一个版本有突破性改变，则 Footer 以 BREAKING CHANGE 开头，后面是对变动的描述、以及变动的理由。

关闭缺陷

如果当前提交是针对特定的 issue，那么可以在 Footer 部分填写需要关闭的单个 issue 或一系列 issues。


#### 参考例子
feat
```
feat(browser): onUrlChange event (popstate/hashchange/polling)

Added new event to browser:
- forward popstate event if available
- forward hashchange event if popstate not available
- do polling when neither popstate nor hashchange available

Breaks $browser.onHashChange, which was removed (use onUrlChange instead)
```

fix
```
fix(compile): couple of unit tests for IE9

Older IEs serialize html uppercased, but IE9 does not...
Would be better to expect case insensitive, unfortunately jasmine does
not allow to user regexps for throw expectations.

Closes #392
Breaks foo.bar api, foo.baz should be used instead
```

style
```
style(location): add couple of missing semi colons
```

chore
```
chore(release): v3.4.2
```

执行 git commit 时使用 emoji 为本次提交打上一个 "标签", 使得此次 commit 的主要工作得以凸现，也能够使得其在整个提交历史中易于区分与查找。

| emoji	| emoji 代码 | commit 说明 |
| ------- | ------- |  ------- |
| 🎉 (庆祝) | `:tada:` | 初次提交 |
| ✨ (火花) | `:sparkles:` | 引入新功能 |
| 🔖 (书签) | `:bookmark:` | 发行/版本标签 |
| 🐛 (bug) | `:bug:` | 修复 bug |
| 🚑 (急救车) | `:ambulance:` | 重要补丁 |
| 🌐 (地球) | `:globe_with_meridians:` | 国际化与本地化 |
| 💄 (口红) | `:lipstick:` | 更新 UI 和样式文件 |
| 🎬 (场记板) | `:clapper:` | 更新演示/示例 |
| 🚨 (警车灯) | `:rotating_light:` | 移除 linter 警告 |
| 🔧 (扳手) | `:wrench:` | 修改配置文件 |
| ➕ (加号) | `:heavy_plus_sign:` | 增加一个依赖 |
| ➖ (减号) | `:heavy_minus_sign:` | 减少一个依赖 |
| ⬆️ (上升箭头) | `:arrow_up:` | 升级依赖 |
| ⬇️ (下降箭头) | `:arrow_down:` | 降级依赖 |
| ⚡️ (闪电) | `:zap:` | 提升性能 |
| 🐎 (赛马) | `:racehorse:` | 提升性能 |
| 📈 (上升趋势图) | `:chart_with_upwards_trend:` | 添加分析或跟踪代码 |
| 🚀 (火箭) | `:rocket:` | 部署功能 |
| ✅ (白色复选框) | `:white_check_mark:` | 增加测试 |
| 📝 (备忘录) | `:memo:` | 撰写文档 |
| 🔨 (锤子) | `:hammer:` | 重大重构 |
| 🎨 (调色板) | `:art:` | 改进代码结构/代码格式 |
| 🔥 (火焰) | `:fire:` | 移除代码或文件 |
| ✏️ (铅笔) | `:pencil2:` | 修复 typo |
| 🚧 (施工) | `:construction:` | 工作进行中 |
| 👷 (工人) | `:construction_worker:` | 添加 CI 构建系统 |
| 💚 (绿心) | `:green_heart:` | 修复 CI 构建问题 |
| 🔒 (锁) | `:lock:` | 修复安全问题 |
| 🐳 (鲸鱼) | `:whale:` | Docker 相关工作 |
| 🍎 (苹果) | `:apple:` | 修复 macOS 下的问题 |
| 🐧 (企鹅) | `:penguin:` | 修复 Linux 下的问题 |
| 🏁 (旗帜) | `:checked_flag:` | 修复 Windows 下的问题 |
