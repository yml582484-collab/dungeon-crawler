# 🚀 地牢游戏 - 公网部署指南

## 📋 部署方式选择

### 方式1: Netlify (推荐⭐) - 最简单！
**优点**: 免费无限项目 | 拖拽部署 | 自动HTTPS | 全球CDN  
**时间**: 2分钟

### 方式2: Vercel - 同样简单
**优点**: 免费无限项目 | 极速部署 | 边缘网络  
**时间**: 2分钟

### 方式3: GitHub Pages - 需要Git
**优点**: 完全免费 | 与GitHub集成  
**时间**: 5-10分钟

---

## ⭐ 方式1: Netlify 部署 (推荐)

### 步骤1: 准备文件 ✅
你的游戏文件已就绪:
- [k.html](./k.html) - 主游戏文件 (包含所有代码)

### 步骤2: 访问 Netlify
1. 打开浏览器访问: **https://app.netlify.com/drop**
2. 登录/注册 (可用GitHub/Google/Email账号)

### 步骤3: 拖拽部署 🎯
1. 将 `k.html` 文件**直接拖拽到页面中间的虚线框**
2. 等待几秒...
3. **完成!** 你的游戏已经上线!

### 步骤4: 获取链接 🌐
部署成功后你会看到:
- **站点URL**: 类似 `https://xxx-app.netlify.app`
- 这就是你可以分享给朋友的链接!

### 步骤5: 自定义域名(可选)
- 点击 "Domain settings"
- 可以添加你自己的域名,如 `dungeon.yourname.com`

---

## 🔧 方式2: Vercel 部署

### 步骤1: 安装 Vercel CLI (可选)
```bash
npm i -g vercel
```

### 步骤2: 网页部署
1. 访问: **https://vercel.com/new**
2. 导入项目或拖拽文件夹
3. 框架选 "Other"
4. 根目录保持默认
5. 点击 "Deploy"

### 步骤3: 完成!
获得类似 `https://xxx.vercel.app` 的链接

---

## 💾 方式3: GitHub Pages

### 步骤1: 创建GitHub仓库
1. 在GitHub创建新仓库: `dungeon-multiplayer`
2. 上传 `k.html` 到仓库

### 步骤2: 启用Pages
1. 进入仓库 → Settings → Pages
2. Source选 "Deploy from branch"
3. Branch选 `main`, `/ (root)`
4. 点击 Save

### 步骤3: 等待部署
几分钟后获得: `https://yourusername.github.io/dungeon-multiplayer/`

---

## 🎮 部署后测试清单

部署完成后,请验证以下功能:

### 基础功能 ✅
- [ ] 页面正常加载
- [ ] 单人模式可玩
- [ ] Firebase连接成功 (控制台显示"✅ Firebase 已就绪!")

### 联机功能 ✅
- [ ] 点击"👥 双人合作"无报错
- [ ] 能创建房间
- [ ] 能看到房间列表
- [ ] 房间号生成正常

### 分享测试 👥
- [ ] 复制链接在新标签页打开
- [ ] 朋友能通过链接访问
- [ ] 两人能同时在线
- [ ] 能看到对方的角色(P2蓝色角色)

---

## 🔗 分享链接示例

部署成功后,你的分享信息:

```
🎮 地牢双人联机 - 邀请一起打怪!

🌐 游戏链接: https://your-game.netlify.app

📖 游戏说明:
1. 打开链接
2. 点击 "👥 双人合作"
3. 创建房间或加入朋友的房间
4. 一起在地牢中冒险!

⚔️ 操作说明:
- 玩家1: WASD移动 + 空格攻击
- 玩家2: 方向键移动 + Enter攻击
```

---

## ⚠️ 注意事项

### Firebase 安全
- API Key公开是正常的(Firebase设计如此)
- 数据库当前为**测试模式**(30天)
- 生产环境建议收紧安全规则

### 性能优化
- 首次加载可能较慢(Firebase SDK)
- 后续加载会快(缓存)
- 建议使用Chrome/Edge/Firefox最新版

### 浏览器兼容
- ✅ Chrome 80+
- ✅ Firefox 75+
- ✅ Safari 13+
- ✅ Edge 80+
- ❌ IE (不支持)

---

## 🛠️ 高级配置 (可选)

### 自定义域名
在Netlify/Vercel设置中添加你的域名:
1. 购买域名 (Namecheap, GoDaddy等)
2. DNS指向Netlify/Vercel
3. 自动HTTPS证书

### 数据库规则更新 (30天后)
登录 [Firebase Console](https://console.firebase.google.com):
→ Realtime Database → Rules → 更改为生产规则:

```json
{
  "rules": {
    "dungeon_rooms": {
      "$roomid": {
        ".read": true,
        ".write": "auth != null"
      }
    },
    ".read": false,
    ".write": false
  }
}
```

---

## 🎯 推荐部署流程

**最快方式 (2分钟)**:
1. 打开 https://app.netlify.com/drop
2. 拖入 k.html
3. 复制生成的链接
4. 发给朋友! 🚀

**祝你游戏愉快!** ⚔️👥🎮
