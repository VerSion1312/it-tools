![logo](.github/logo.png)

本项目是从 [CorentinTh/it-tools](https://github.com/CorentinTh/it-tools) `fork`而来的。

## 如何开发及部署

### IDE设置推荐

推荐使用[VSCode](https://code.visualstudio.com/) 进行开发，并建议安装以下扩展:

- [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar) (and disable Vetur)
- [TypeScript Vue Plugin (Volar)](https://marketplace.visualstudio.com/items?itemName=Vue.vscode-typescript-vue-plugin).
- [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)
- [i18n Ally](https://marketplace.visualstudio.com/items?itemName=lokalise.i18n-ally)

并在VSCode的配置文件中添加:

```json
{
  "editor.formatOnSave": false,
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": true
  },
  "i18n-ally.localesPaths": ["locales", "src/tools/*/locales"],
  "i18n-ally.keystyle": "nested"
}
```

### 如何在写TS时添加`vue`文件的引用

默认情况下，TypeScript无法处理`.vue`导入的类型信息，因此我们将`tsc`CLI替换为`vue-tsc`进行类型检查。在编辑器中，我们需要 [TypeScript Vue Plugin (Volar)](https://marketplace.visualstudio.com/items?itemName=Vue.vscode-typescript-vue-plugin) ，以使typescript语言服务知道`.vue`类型。

If the standalone TypeScript plugin doesn't feel fast enough to you, Volar has also implemented a [Take Over Mode](https://github.com/johnsoncodehk/volar/discussions/471#discussioncomment-1361669) that is more performant. You can enable it by the following steps:

如果你觉得独立的TypeScript插件不够快，Volar还实现了 [托管模式](https://github.com/johnsoncodehk/volar/discussions/471#discussioncomment-1361669) 更具性能。您可以通过以下步骤启用它：

1. 禁用内置的TypeScript扩展
   1. 在VSCode的指令输入框中输入`Extensions: Show Built-in Extensions`
   2. 找到`TypeScript and JavaScript Language Features`，右键并选择`Disable (Workspace)`
2. 在指令输入框中输入 `Developer: Reload Window` 以重新加载VSCode。

### 依赖安装

```sh
npm install
```

### 开发时的编译和热重载

```sh
npm run dev
```

### 编译和生成可发布文件包

```sh
npm run build
```

### 使用 [Vitest](https://vitest.dev/) 进行单元测试

```sh
npm run test
```

### 使用 [ESLint](https://eslint.org/) 进行检查

```sh
npm run lint
```

### 添加新的工具

如果要创建一个新的工具，可以运行预先设置好的脚本，运行以下指令：

```sh
npm run script:create:tool my-tool-name
```

它将在`src/tools`中创建一个包含正确文件的目录，并在`src/tools/index.ts`中创建导入。您只需要将导入的工具添加到适当的类别中并开发该工具。

## 开源许可

本项目基于 [GNU GPLv3](LICENSE) 开源许可。
