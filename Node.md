# NodeJS

## Tips

**how config yarn use chinese taobao npm mirror**


`npm config set registry https://registry.npm.taobao.org`

source: https://github.com/yarnpkg/yarn/issues/2411

**how config yarn use chinese tencent npm mirror**

`npm config set registry http://mirrors.cloud.tencent.com/npm/`


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

**npm update packages**

```
npm install -g npm-check-updates
ncu -u
```

[Update all the Node dependencies to their latest version](https://flaviocopes.com/update-npm-dependencies/)

- <https://stackoverflow.com/questions/10068592/how-do-i-update-devdependencies-in-npm>
- <https://flaviocopes.com/update-npm-dependencies/>
- <https://yarnpkg.com/lang/en/docs/managing-dependencies/>
- <https://yarnpkg.com/lang/en/docs/cli/upgrade/>


## yarn

**use an older version**

`yarn policies set-version 1.18.0`

[ "Incorrect integrity when fetching from the cache" #7584 ](https://github.com/yarnpkg/yarn/issues/7584)