## 下载

网址：[Github 发布页](https://github.com/Molunerfinn/PicGo/releases)

## 配置

[官方介绍](https://github.com/PicGo/PicGo-Doc/tree/master/docs/zh/guide)

### 配置备份

```
{
  "uploaded": [
    {
      "fileName": "20200805032547.png",
      "id": "1e42ddfa84d8ce8910ffa5fd5a8b3b1d1cf89412",
      "sha": "1e42ddfa84d8ce8910ffa5fd5a8b3b1d1cf89412",
      "extname": "png",
      "imgUrl": "https://raw.githubusercontent.com/Soanguy/imgbak/master/img/20200805032547.png",
      "type": "githubPlus"
    }
  ],
  "picBed": {
    "current": "githubPlus",
    "github": {
      "branch": "master",
      "customUrl": "",
      "path": "img/",
      "repo": "Soanguy/imgbak",
      "token": "![](https://raw.githubusercontent.com/Soanguy/imgbak/master/img/JS-Intro-p1.png)"
    },
    "list": [
      {
        "name": "SM.MS图床",
        "type": "smms",
        "visible": false
      },
      {
        "name": "腾讯云COS",
        "type": "tcyun",
        "visible": false
      },
      {
        "name": "微博图床",
        "type": "weibo",
        "visible": false
      },
      {
        "name": "GitHub图床",
        "type": "github",
        "visible": true
      },
      {
        "name": "七牛图床",
        "type": "qiniu",
        "visible": false
      },
      {
        "name": "Imgur图床",
        "type": "imgur",
        "visible": false
      },
      {
        "name": "阿里云OSS",
        "type": "aliyun",
        "visible": false
      },
      {
        "name": "又拍云图床",
        "type": "upyun",
        "visible": false
      }
    ],
    "githubPlus": {
      "branch": "master",
      "customUrl": "",
      "origin": "github",
      "path": "img/",
      "repo": "Soanguy/imgbak",
      "token": "e240dd7c874b12353a09328bc463a7eb8733443d"
    }
  },
  "settings": {
    "shortKey": {
      "picgo:upload": {
        "enable": true,
        "key": "CommandOrControl+Shift+u",
        "name": "upload",
        "label": "快捷上传"
      }
    },
    "server": {
      "port": 36677,
      "host": "127.0.0.1",
      "enable": true
    },
    "showUpdateTip": false,
    "autoStart": true,
    "rename": true,
    "uploadNotification": true
  },
  "picgoPlugins": {
    "picgo-plugin-github-plus": true
  },
  "debug": true,
  "PICGO_ENV": "GUI",
  "needReload": false,
  "picgo-plugin-github-plus": {
    "lastSync": "2020-09-01 09:35:29"
  }
}
```

## 插件

### GitHub-Plus

可以管理上传的图片，即使重新安装软件也可以通过 Pull origin 来拉去仓库里曾经上传了的照片。

![](https://raw.githubusercontent.com/Soanguy/imgbak/master/img/PicGo-p1.png)

## 问题解决

### Bad credentials

解决方法：返回 Github，重新生成 `token` 即可。

出现该问题的可能原因：将图片仓库设定为不可见后导致的 `token` 丢失。因此无法上传。

> 实际产生该问题的原因有可能是因为 在上传至 Github 的文件当中含有密钥，Github 自动将密钥删除