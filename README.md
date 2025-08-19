# Sign_Bot
app下载：https://play.google.com/store/apps/details?id=global.sign.orange

推荐码： G6CY6158P6

# Sign.global 自动登录签到工具

一个自动化的Sign.global账户管理工具，支持多账户、代理、定时运行等功能。

## 目录结构

```
sign/
├── bot                     # 主程序文件
├── config/                 # 配置文件目录
│   ├── config.json         # 主配置文件
│   ├── accounts.txt        # 账户列表
│   ├── proxy.txt           # 代理列表
│   ├── rf.txt              # 邀请码
│   ├── comment.txt         # 评论内容
└── login_cache/            # 登录缓存目录（自动创建）
    ├── user1_at_example_com.json
    └── user2_at_example_com.json
```

## 配置文件说明

### config/config.json
```json
{
  "run_interval": {
    "min_hours": 1,    // 最小运行间隔（小时）
    "max_hours": 1     // 最大运行间隔（小时）
  },
  "processing_mode": {
    "concurrent": false,    // 处理模式：true为并发，false为循环
    "max_workers": 3        // 最大并发数
  },
  "display_settings": {
    "show_progress": true,
    "show_detailed_logs": true
  },
  "cache_settings": {
    "login_cache_expire_hours": 24  // 登录缓存过期时间
  }
}
```

### accounts.txt
```
# 每行一个邮箱地址
farahman909@gmail.com
user2@example.com
user3@example.com
```

### proxy.txt
```
# 每行一个代理服务器
http://192.168.2.51:7009
socks5://proxy2.example.com:1080
http://proxy3.example.com:8080
```

### rf.txt
```
# 邀请码
G6CY6158P6
```

### comment.txt
```
# 评论内容，每行一条
LFG
Great post! 🚀
Amazing content! 👏
Love this! ❤️
```


## 功能特性

- ✅ **多账户支持**：支持循环和并发两种处理模式
- ✅ **代理支持**：每个账户对应一个代理
- ✅ **登录缓存**：避免重复登录，提高效率
- ✅ **定时运行**：每小时随机时间运行一次
- ✅ **自动签到**：登录后自动签到
- ✅ **帖子互动**：自动点赞、评论、打赏
- ✅ **用户信息**：显示账户详细信息
- ✅ **优雅停止**：支持安全停止程序
- ✅ **并发处理**：可配置最大并发数，提高处理效率

## 注意事项

1. 首次运行需要输入验证码，后续运行会使用缓存
2. 登录缓存有效期为24小时（可配置）
3. 程序会无限循环运行，直到手动停止
4. 建议使用代理以避免IP限制
5. 请合理设置运行间隔，避免过于频繁的请求
6. 并发模式下，建议合理设置最大并发数，避免服务器压力过大
7. 按一次 Ctrl+C 优雅停止，按两次强制退出

## 故障排除

- **配置文件不存在**：程序会使用默认配置
- **代理连接失败**：会自动尝试其他代理或直接连接
- **登录失败**：会清除缓存并重新登录
- **缓存过期**：会自动重新登录并更新缓存
