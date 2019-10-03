# NodeJS

## Tips

**how config yarn use chinese taobao npm mirror**


`npm config set registry https://registry.npm.taobao.org`

source: https://github.com/yarnpkg/yarn/issues/2411

**`Yarn global add` on Windows**

Executables will be installed to `%LOCALAPPDATA%\Yarn\bin`

Or you can specify a custom path:

```
mkdir ~/yarn-global
yarn config set prefix ~/yarn-global
```

[Where does Yarn add global binaries on Windows?](https://stackoverflow.com/questions/40258322/where-does-yarn-add-global-binaries-on-windows)

**unpack electron archive**

```
yarn global add asar
```

```
npx asar extract app.asar destfolder 
npx asar extract-file app.asar main.js
```

[How to unpack an .asar file?](https://stackoverflow.com/questions/38523617/how-to-unpack-an-asar-file)

