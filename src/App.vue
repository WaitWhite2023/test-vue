<script setup lang="ts">
const posts = [
  {
    title: 'Vue 3 组合式 API 入门笔记',
    date: '2026-05-20',
    summary: '记录学习 Vue 3 Composition API 的过程，包括 setup 语法糖、响应式基础和常用组合式函数。',
    tag: 'Vue'
  },
  {
    title: '用 Vite 搭建前端项目的最佳实践',
    date: '2026-04-12',
    summary: '从项目初始化到生产环境部署，整理了一套基于 Vite 的前端工程化实践方案。',
    tag: '工程化'
  },
  {
    title: 'TypeScript 类型体操小记',
    date: '2026-03-08',
    summary: '深入理解 TypeScript 的高级类型系统，通过几个实际案例练习类型推导和泛型编程。',
    tag: 'TypeScript'
  },
  {
    title: '2026 年初的一些生活随笔',
    date: '2026-01-15',
    summary: '关于新年计划、阅读习惯和技术学习路线的一些零散思考。',
    tag: '随笔'
  }
]
</script>

<template>
  <header class="site-header">
    <div class="site-brand">
      <span class="brand-avatar">林</span>
      <span>林小北的博客</span>
    </div>
    <nav class="site-nav">
      <a href="#" class="active">首页</a>
      <a href="#">归档</a>
      <a href="#">关于</a>
    </nav>
  </header>

  <main class="site-main">
    <section class="intro">
      <div class="intro-card">
        <div class="intro-avatar">
          <span>林</span>
        </div>
        <div class="intro-content">
          <h1>你好，我是林小北</h1>
          <p class="intro-desc">一名前端开发者，喜欢写代码、读小说和徒步旅行。这里是我记录技术笔记与生活点滴的地方。</p>
          <div class="intro-stats">
            <div class="stat">
              <span class="stat-num">4</span>
              <span class="stat-label">文章</span>
            </div>
            <div class="stat">
              <span class="stat-num">2</span>
              <span class="stat-label">标签</span>
            </div>
            <div class="stat">
              <span class="stat-num">128</span>
              <span class="stat-label">天前开始</span>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section class="post-list">
      <div class="section-header">
        <h2 class="section-title">最新文章</h2>
        <a href="#" class="section-more">查看全部 →</a>
      </div>
      <article v-for="post in posts" :key="post.title" class="post-item">
        <div class="post-meta">
          <span class="post-tag">{{ post.tag }}</span>
          <time class="post-date">{{ post.date }}</time>
        </div>
        <h3 class="post-title">
          <a href="#">{{ post.title }}</a>
        </h3>
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
  padding: 24px 0;
  border-bottom: 1px solid var(--border);
}

.site-brand {
  display: flex;
  align-items: center;
  gap: 12px;
  font-size: 18px;
  font-weight: 600;
  color: var(--text-h);
}

.brand-avatar {
  width: 36px;
  height: 36px;
  display: flex;
  align-items: center;
  justify-content: center;
  background: var(--accent);
  color: #fff;
  font-size: 15px;
  font-weight: 600;
  border-radius: 10px;
}

.site-nav {
  display: flex;
  gap: 8px;
}

.site-nav a {
  padding: 6px 14px;
  border-radius: 8px;
  color: var(--text-light);
  font-size: 14px;
  font-weight: 500;
  text-decoration: none;
  transition: all 0.2s ease;
}

.site-nav a:hover {
  color: var(--text);
  background: var(--accent-bg);
}

.site-nav a.active {
  color: var(--accent);
  background: var(--accent-bg);
}

.site-main {
  flex: 1;
  padding: 32px 0 48px;
}

.intro {
  margin-bottom: 48px;
}

.intro-card {
  display: flex;
  gap: 24px;
  align-items: flex-start;
  padding: 32px;
  background: var(--accent-bg);
  border-radius: 20px;
  border: 1px solid var(--border);
  transition: box-shadow 0.3s ease;
}

.intro-card:hover {
  box-shadow: 0 8px 30px rgba(0, 0, 0, 0.06);
}

.intro-avatar {
  flex-shrink: 0;
  width: 72px;
  height: 72px;
  display: flex;
  align-items: center;
  justify-content: center;
  background: var(--accent);
  color: #fff;
  font-size: 28px;
  font-weight: 700;
  border-radius: 20px;
  box-shadow: 0 4px 14px rgba(79, 70, 229, 0.3);
}

.intro-content {
  flex: 1;
}

.intro h1 {
  font-size: 26px;
  margin-bottom: 10px;
  letter-spacing: -0.3px;
}

.intro-desc {
  font-size: 15px;
  color: var(--text-light);
  line-height: 170%;
  margin-bottom: 20px;
}

.intro-stats {
  display: flex;
  gap: 24px;
}

.stat {
  display: flex;
  flex-direction: column;
  gap: 2px;
}

.stat-num {
  font-size: 18px;
  font-weight: 700;
  color: var(--text-h);
  line-height: 1;
}

.stat-label {
  font-size: 12px;
  color: var(--text-light);
}

.section-header {
  display: flex;
  align-items: baseline;
  justify-content: space-between;
  margin-bottom: 20px;
}

.section-title {
  font-size: 13px;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 1px;
  color: var(--text-light);
  margin: 0;
}

.section-more {
  font-size: 13px;
  font-weight: 500;
  color: var(--text-light);
  text-decoration: none;
  transition: color 0.2s ease;
}

.section-more:hover {
  color: var(--accent);
  text-decoration: none;
}

.post-item {
  padding: 24px;
  margin-bottom: 16px;
  background: var(--bg);
  border: 1px solid var(--border);
  border-radius: 16px;
  transition: all 0.25s ease;
  position: relative;
}

.post-item:hover {
  border-color: transparent;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.08);
  transform: translateY(-2px);
}

.post-item:last-child {
  margin-bottom: 0;
}

.post-meta {
  display: flex;
  align-items: center;
  gap: 12px;
  margin-bottom: 10px;
}

.post-tag {
  display: inline-flex;
  align-items: center;
  padding: 2px 10px;
  font-size: 12px;
  font-weight: 500;
  color: var(--accent);
  background: var(--accent-bg);
  border-radius: 6px;
}

.post-date {
  font-size: 13px;
  color: var(--text-light);
}

.post-title {
  font-size: 18px;
  font-weight: 600;
  margin: 0 0 8px;
  line-height: 1.4;
}

.post-title a {
  color: var(--text-h);
  text-decoration: none;
  transition: color 0.2s ease;
}

.post-title a:hover {
  color: var(--accent);
}

.post-summary {
  font-size: 15px;
  line-height: 160%;
  color: var(--text-light);
  margin: 0;
}

.site-footer {
  padding: 24px 0 32px;
  border-top: 1px solid var(--border);
  text-align: center;
}

.site-footer p {
  font-size: 13px;
  color: var(--text-light);
}

@media (max-width: 520px) {
  .intro-card {
    flex-direction: column;
    align-items: center;
    text-align: center;
    gap: 20px;
  }

  .intro-stats {
    justify-content: center;
  }

  .site-header {
    flex-direction: column;
    gap: 16px;
    text-align: center;
  }
}
</style>
