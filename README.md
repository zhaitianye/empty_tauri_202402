# 空的 tauri 快速打包 基于 rust webview2

## 图标替换

1. `./src-tauri/icons/icon.png` 替换为你的图标，512\*512
2. 执行命令 `yarn tauri:icons:generate` 一键生成图标

## 打包配置

设置 tauri.conf.json

### 更换名称

```json
{
  "package": {
    "productName": "应用名称"
  }
}
```

### 更换包空间

```json
{
  "tauri": {
    "bundle": {
      "identifier": "com.namespace.packagename"
    }
  }
}
```

### 禁用安全 web-security

```json
{
  "tauri": {
    "windows": [
      {
        "additionalBrowserArgs": "--disable-web-security"
      }
    ]
  }
}
```

### 使用本地项目

```json
{
  "build": {
    "beforeDevCommand": "yarn dev",
    "beforeBuildCommand": "yarn build",
    "devPath": "http://localhost:1420",
    "distDir": "../dist"
  }
}
```

### 使用线上项目

```json
{
  "tauri": {
    "windows": [
      {
        "title": "xxx",
        "url": "https://www.baidu.com"
      }
    ]
  }
}
```
