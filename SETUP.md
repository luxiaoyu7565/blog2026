# 部署说明

这次更新把图片和附件改为 Firebase Storage 保存，避免把大文件塞进 Firestore。

## 只需做一次

1. 在 Firebase Console 打开项目 `blog-6dd2d`，启用 **Storage**。
2. 在 Storage 的「规则」页面粘贴并发布仓库中的 `storage.rules`。
3. 在 Firestore 的「规则」页面粘贴并发布更新后的 `firestore.rules`。
4. 为防止评论被机器人批量发布：在 Firebase Console 的 **App Check** 中为 Firestore 注册网页应用并启用强制执行。此项需要你按控制台提示配置 reCAPTCHA Enterprise。

网站本身还包含了 60 秒评论间隔与隐藏字段拦截；它们能减少普通垃圾评论，但不能替代 App Check。
