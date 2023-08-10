## hydra 
hydra译为“九头蛇”，该项目是一个多项目管理工具cli，可以用来对多个项目进行安装依赖，单独/多个打包，单独/多个发布、运行等管理操作。

### 使用方法
- 在自己的项目package.json中配置
```
   hydra?: {
    devLinks?: string[] // 子项目的项目名，表示该项目还依赖某些子项目，在安装该项目依赖之前会先安装devLinks中的项目
    type?: 'service' | 'app' | 'lib' | 'cli'
    port?: number // 仅在type: service时使用
  }
```
- 然后将本项目安装在需要管理的多项目的根目录后执行packjson中的命令即可，如：
```
yarn install-deps // 安装所有项目deps中的依赖
yarn install-dep xxx // 安装指定项目deps中的依赖
yarn install-links // 安装所有项目本地依赖
yarn install-link xxx // 安装指定项目本地依赖
yarn dev xxx
yarn serve xxx
yarn build xxx
```
