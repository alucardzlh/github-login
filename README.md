# Urodele Github Login

这是一个帮助用户使用Github App方式登录使用urodele创建的博客站点的项目[urodele-blog](https://github.com/apps/urodele-blog)，基于免费的cloudflare worker

# 如何使用

首先你需要使用urodele创建一个站点，然后向该项目创建一个PR，将你的博客域名 https://YOUR_NAME.github.io 增加到white_list中

PR通过后，在你的博客仓库urodele.config.ts中，填入如下配置：
```typescript
export const config = {
  github: {
    // ... other options
    logInUrl:
      "https://github-login.link-ai.workers.dev/api/oauth/authorize?redirect_uri=https://YOUR_NAME.github.io/login",
    logInAuthUrl: "https://github-login.link-ai.workers.dev/api/oauth/token",
  },
  // ... other options
}
```

之后即可在自己博客站点中使用Github App方式登录

如果你想要创建私有的Github App来登录，你也可以fork本仓库，或者通过阅读这篇文章来了解如何自定义App登录链接
