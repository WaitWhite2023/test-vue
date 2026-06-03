<script setup lang="ts">
const posts = [
  {
    title: 'Vue 3 组合式 API 入门笔记',
    date: '2026-05-20',
    summary: '记录学习 Vue 3 Composition API 的过程，包括 setup 语法糖、响应式基础和常用组合式函数。'
  },
  {
    title: '用 Vite 搭建前端项目的最佳实践',
    date: '2026-04-12',
    summary: '从项目初始化到生产环境部署，整理了一套基于 Vite 的前端工程化实践方案。'
  },
  {
    title: 'TypeScript 类型体操小记',
    date: '2026-03-08',
    summary: '深入理解 TypeScript 的高级类型系统，通过几个实际案例练习类型推导和泛型编程。'
  },
  {
    title: '2026 年初的一些生活随笔',
    date: '2026-01-15',
    summary: '关于新年计划、阅读习惯和技术学习路线的一些零散思考。'
  }
]
</script>

<template>
  <header class="site-header">
    <div class="site-brand">林小北的博客</div>
    <nav class="site-nav">
      <a href="#">首页</a>
      <a href="#">归档</a>
      <a href="#">关于</a>
    </nav>
  </header>

  <main class="site-main">
    <section class="intro">
      <h1>你好，我是林小北</h1>
      <p class="intro-desc">一名前端开发者，喜欢写代码、读小说和徒步旅行。这里是我记录技术笔记与生活点滴的地方。</p>
    </section>

    <section class="post-list">
      <h2 class="section-title">最新文章</h2>
      <article v-for="post in posts" :key="post.title" class="post-item">
        <h3 class="post-title">
          <a href="#">{{ post.title }}</a>
        </h3>
        <time class="post-date">{{ post.date }}</time>
        <p class="post-summary">{{ post.summary }}</p>
      </article>
    </section>
  </main>

  <footer class="site-footer">
    <p>© 2026 林小北的博客 · 由 Vue 3 + Vite 驱动</p>
  </footer>
</template>

<style scoped>
.site-header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 32px 0 24px;
  border-bottom: 1px solid var(--border);
}

.site-brand {
  font-size: 20px;
  font-weight: 600;
  color: var(--text-h);
}

.site-nav {
  display: flex;
  gap: 24px;
}

.site-nav a {
  color: var(--text);
  font-size: 15px;
  text-decoration: none;
}

.site-nav a:hover {
  color: var(--accent);
}

.site-main {
  flex: 1;
  padding: 40px 0;
}

.intro {
  margin-bottom: 48px;
}

.intro h1 {
  font-size: 32px;
  margin-bottom: 12px;
}

.intro-desc {
  font-size: 16px;
  color: var(--text-light);
  max-width: 560px;
  line-height: 170%;
}

.section-title {
  font-size: 14px;
  font-weight: 500;
  text-transform: uppercase;
  letter-spacing: 0.5px;
  color: var(--text-light);
  margin-bottom: 24px;
}

.post-item {
  padding: 20px 0;
  border-bottom: 1px solid var(--border);
}

.post-item:first-of-type {
  padding-top: 0;
}

.post-title {
  font-size: 18px;
  font-weight: 600;
  margin-bottom: 6px;
}

.post-title a {
  color: var(--text-h);
}

.post-title a:hover {
  color: var(--accent);
  text-decoration: none;
}

.post-date {
  display: block;
  font-size: 14px;
  color: var(--text-light);
  margin-bottom: 8px;
}

.post-summary {
  font-size: 15px;
  line-height: 160%;
  color: var(--text);
}

.site-footer {
  padding: 24px 0 32px;
  border-top: 1px solid var(--border);
  text-align: center;
}

.site-footer p {
  font-size: 14px;
  color: var(--text-light);
}
</style>
