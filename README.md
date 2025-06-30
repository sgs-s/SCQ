This is a [Next.js](https://nextjs.org) project bootstrapped with [`create-next-app`](https://nextjs.org/docs/app/api-reference/cli/create-next-app).

## Getting Started

First, run the development server:

```bash
npm run dev
# or
yarn dev
# or
pnpm dev
# or
bun dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

You can start editing the page by modifying `app/page.tsx`. The page auto-updates as you edit the file.

This project uses [`next/font`](https://nextjs.org/docs/app/building-your-application/optimizing/fonts) to automatically optimize and load [Geist](https://vercel.com/font), a new font family for Vercel.

## Learn More

To learn more about Next.js, take a look at the following resources:

- [Next.js Documentation](https://nextjs.org/docs) - learn about Next.js features and API.
- [Learn Next.js](https://nextjs.org/learn) - an interactive Next.js tutorial.

You can check out [the Next.js GitHub repository](https://github.com/vercel/next.js) - your feedback and contributions are welcome!

## Deploy on Vercel

The easiest way to deploy your Next.js app is to use the [Vercel Platform](https://vercel.com/new?utm_medium=default-template&filter=next.js&utm_source=create-next-app&utm_campaign=create-next-app-readme) from the creators of Next.js.

Check out our [Next.js deployment documentation](https://nextjs.org/docs/app/building-your-application/deploying) for more details.
Path: README.md
# Blog Platform with Next.js

## 项目简介
基于Next.js构建的博客平台，集成以下核心功能：
- QAnything知识库问答系统嵌入
- WakaTime开发时长统计集成
- 旧练习作业整合管理系统

## 功能实现细节

### QAnything集成
实现路径：
<mcfile name="page.tsx" path="src/app/practice/embed-demo/page.tsx"></mcfile>
```tsx
// ... existing code ...
<iframe
  src="https://ai.youdao.com/saas/qanything/#/home"
  title="QAnything 问答服务"
/>
// ... existing code ...
```

### WakaTime集成
核心组件：
<mcsymbol name="WakaTimeStats" filename="wakatime-stats.tsx" path="src/app/wakatime-stats.tsx" startline="44" type="function"></mcsymbol>
```tsx
// 环境变量配置
const apiKey = process.env.WAKATIME_API_KEY;

// API请求实现
const url = `https://wakatime.com/api/v1/users/current/all_time_since_today?api_key=${apiKey}`;
```

## 项目结构
```
blog-platform/
├── src/
│   ├── app/
│   │   ├── layout.tsx      # 主布局文件
│   │   ├── wakatime-stats.tsx # 时长统计组件
│   │   └── practice/       # 旧作业整合目录
```

## 运行指南
1. 安装依赖：
```bash
npm install
```
2. 配置环境变量：
```env
WAKATIME_API_KEY=your_api_key
```
3. 启动开发服务器：
```bash
npm run dev
```

