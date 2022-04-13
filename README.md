若想能让 TypeScript 文件能够更加准确感知 JavaScript 文件的类型，你可以为 JavaScript 文件书写类型声明文件(即：后缀为 `.d.ts` 的文件)；默认配置是建义你将 JavaScript 的 类型声明文件`.d.ts` 都放在 `types/` 目录下；

- `npm run build` : 构建项目；
- `npm run dev` : 构建项目，并监听源文件的改动，如果有改动，便会重新打包；
- `npm run test` : 执行 `test/index` 文件；

- `rollup -c` : 构建项目；
- `rollup -c -w` : 构建项目，并监听源文件的改动，如果有改动，便会重新打包；

默认构建输出了以下几种模块格式的包：
- `es`：ESModule
- `cjs`：CommonJS
- `amd`：AMD
- `umd` : umd
- `iife`：自执行

```
rollup-boilerplate/            # 构建前端库的webpack打包配置模板项目根目录
   ├── package.json            # npm 的包管理配置文件
   ├── src/                    # 默认的包含项目源代码的目录
   │   └── index               # 默认的构建入口文件
   ├── test/                   # 默认的包含测试代码的目录
   │   └── index               # 默认的构建入口文件
   ├── dist/                   # 默认的构建输出目录
   ├── LICENSE                 # 开源证可证；默认是 MIT 许可证
   ├── tsconfig.json           # TypeScript 的配置文件
   ├── README.md               # 项目的说明文档
   ├── .eslintignore           # ESLint 的忽略配置文件
   ├── .eslintrc.js            # ESLint 的配置文件
   ├── .gitignore              # git 的忽略配置文件
   └── .npmignore              # npm 上传包时的忽略配置文件
```


- `.npmignore` : npm 上传包时的忽略配置文件；默认忽略了 与构建配置文件的所有文件和目录，如：`build/` 等等；也忽略了开发环境默认的输出目录 `dev/`，还有编辑器相关的文件和目录，如：`.idea`、`.vscode`；
- `package.json` : npm 的包管理配置文件；同时也是 通过 npm 上传、发布 包 的 配置模板文件；
**注意：** `package.json` 文件中的如下字段：
- `module` : 该字段是用来指定以标准模块暴露的出口文件；
- `types` | `typings` ： 该字段是用来指定库的类型声明文件；如果库没有类型声明文件，则去除该字段；
- `"sideEffects" : boolean | Array<string>` ，可以为布尔，表示整个包是否有副作用；也可以是一些有副作用文件的的路径字符串，路径支持 相对路径、绝对路径和 glob 模式； 副作用标记；表明项目中的哪些文件不是 纯的 ES2015 模块，由此不能安全地删除文件中未使用的部分，"side effect(副作用)" 的定义是，在导入时会执行特殊行为的代码，而不是仅仅暴露一个 export 或多个 export。举例说明，例如 polyfill，它影响全局作用域，并且通常不提供 export；详细内容请见 <https://webpack.docschina.org/guides/tree-shaking/#将文件标记为-side-effect-free-无副作用->

_关于`package.json`文件的详细配置信息请参考<https://docs.npmjs.com/files/package.json>_
_关于 Rollup 的详细配置信息请参考<https://rollupjs.org>_
_关于 `tsconfig` 的详细配置信息请参考 <https://www.typescriptlang.org/docs/handbook/tsconfig-json.html>_
_关于 ESLint 的详细配置信息请参考 <http://eslint.cn/docs/user-guide/configuring>_
