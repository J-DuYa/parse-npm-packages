# parse-npm-packages

现阶段支持解析的格式:

- 本地 `package-lock.json` 文件
- 线上 `package-lock.json` 地址
- 包的名字
- 本地 `package.json` 文件
- 线上 `package.json`的地址

## 本地安装

```bash
npm install parse-npm-packages -g
```

## 使用说明

### 在代码中引用:

```js
const downloader = require('parse-npm-packages');

downloader.downloadFromPackageLock('path/to/package-lock');
```

### 使用案例:

#### package-lock.json

从本地文件中导入:

```bash
package-tarball-tgz package-lock path/to/package-lock.json
```

从线上调用:

```bash
package-tarball-tgz package-lock https://raw.githubusercontent.com/Meir017/node-tgz-downloader/master/package-lock.json
```

#### 包名

```base
package-tarball-tgz package @angular/cli --devDependencies --peerDependencies
```

#### package.json

从本地文件导入:

```bash
package-tarball-tgz package-json path/to/package.json
```

从线上调用:

```bash
package-tarball-tgz package-json https://raw.githubusercontent.com/Meir017/node-tgz-downloader/master/package.json
```

#### 搜索关键字

通过调用 npm 接口查询 包信息获取 tarball (https://registry.npmjs.org/-/v1/search?)

```base
package-tarball-tgz search tgz
```

[npm-image]: https://img.shields.io/npm/v/node-tgz-downloader.svg
[npm-url]: https://npmjs.org/package/node-tgz-downloader
[downloads-image]: https://img.shields.io/npm/dm/node-tgz-downloader.svg
[downloads-url]: https://npmjs.org/package/node-tgz-downloader