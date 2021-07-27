十四、antd的按需引入+自定主题
1.安装依赖：npm install react-app-rewired customize-cra babe;-plugin-import less less-loader
2.修改package.json
    "scripts": {
    "start": "react-app-rewired start",
    "build": "react-app-rewired build",
    "test": "react-app-rewired test",
    "eject": "react-scripts eject"
  },
3.根目录下创建config-overrides.js
    const { override, fixBabelImports, addLessLoader } = require('customize-cra');
    module.exports = override(
    fixBabelImports('import', {
        libraryName: 'antd',
        libraryDirectory: 'es',
        style: true,
    }),
    addLessLoader({
        lessOptions:{
            javascriptEnabled: true,
            modifyVars: { '@primary-color': '#1DA57A' },
        }
    }),
);