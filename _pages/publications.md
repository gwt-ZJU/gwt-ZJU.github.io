---
layout: page
permalink: /publications/
title: 论文 @ publications
description: 按年份倒序排列的论文列表，支持 全部 / 精选 / 合作 筛选。
nav: true
nav_order: 2
---

<!-- _pages/publications.md -->

<!-- 全部 / 精选 / 合作 筛选标签 -->
<style>
  .pub-tabs {
    display: flex;
    gap: 0.5rem;
    margin-bottom: 1.5rem;
    flex-wrap: wrap;
  }
  .pub-tab {
    border: 1px solid var(--global-divider-color);
    background: var(--global-bg-color);
    color: var(--global-text-color);
    border-radius: 999px;
    padding: 0.3rem 1.1rem;
    font-size: 0.95rem;
    cursor: pointer;
    transition: all 0.15s ease;
  }
  .pub-tab:hover {
    border-color: var(--global-theme-color);
    color: var(--global-theme-color);
  }
  .pub-tab.active {
    background: var(--global-theme-color);
    border-color: var(--global-theme-color);
    color: var(--global-bg-color);
  }
  .pub-tab .pub-tab-count {
    opacity: 0.75;
    margin-left: 0.3rem;
    font-size: 0.85em;
  }
  /* 我的名字蓝色高亮 */
  .author-self {
    color: #1a6fc4;
    font-weight: 600;
  }
  /* 通讯作者图例 */
  .pub-legend {
    font-size: 0.88rem;
    color: var(--global-text-color-light, #747373);
    margin-bottom: 1rem;
  }
  .pub-legend .author-self {
    font-weight: 600;
  }
</style>

<div class="pub-tabs" id="pub-tabs">
  <button class="pub-tab active" data-filter="all"><span class="lang-zh">全部</span><span class="lang-en">All</span><span class="pub-tab-count"></span></button>
  <button class="pub-tab" data-filter="featured"><span class="lang-zh">精选</span><span class="lang-en">Featured</span><span class="pub-tab-count"></span></button>
  <button class="pub-tab" data-filter="collaboration"><span class="lang-zh">合作</span><span class="lang-en">Collaborations</span><span class="pub-tab-count"></span></button>
</div>

<div class="publications">

{% bibliography %}

</div>

<script>
  (function () {
    var container = document.querySelector('.publications');
    if (!container) return;
    var entries = container.querySelectorAll('.row[class*="pub-cat-"]');
    // 统计各分类数量
    var counts = { all: entries.length, featured: 0, collaboration: 0 };
    entries.forEach(function (e) {
      if (e.classList.contains('pub-cat-featured')) counts.featured++;
      if (e.classList.contains('pub-cat-collaboration')) counts.collaboration++;
    });
    document.querySelectorAll('.pub-tab').forEach(function (btn) {
      var span = btn.querySelector('.pub-tab-count');
      if (span) span.textContent = '(' + counts[btn.dataset.filter] + ')';
    });
    // 标签切换：过滤条目 + 隐藏空年份分组
    // DOM 结构：<h2>年份</h2> + <ol>（内含 <li> 条目，条目里是 div.row.pub-cat-*）
    function applyFilter(filter) {
      // 1. 显示/隐藏每个条目（隐藏整个 li，避免残留空白）
      entries.forEach(function (el) {
        var li = el.closest('li') || el;
        var show =
          filter === 'all' ||
          (filter === 'featured' && el.classList.contains('pub-cat-featured')) ||
          (filter === 'collaboration' && el.classList.contains('pub-cat-collaboration'));
        li.style.display = show ? '' : 'none';
      });
      // 2. 年份分组：ol 里没有可见条目时，隐藏 ol 和它前面的年份标题 h2
      var children = Array.from(container.children);
      children.forEach(function (el) {
        if (el.tagName !== 'OL') return;
        var hasVisible = Array.from(el.querySelectorAll('li')).some(function (li) {
          return li.style.display !== 'none';
        });
        el.style.display = hasVisible ? '' : 'none';
        var idx = children.indexOf(el);
        for (var i = idx - 1; i >= 0; i--) {
          if (children[i].tagName === 'H2') {
            children[i].style.display = hasVisible ? '' : 'none';
            break;
          }
        }
      });
    }
    document.getElementById('pub-tabs').addEventListener('click', function (e) {
      var btn = e.target.closest('.pub-tab');
      if (!btn) return;
      document.querySelectorAll('.pub-tab').forEach(function (b) { b.classList.remove('active'); });
      btn.classList.add('active');
      applyFilter(btn.dataset.filter);
    });
  })();
</script>
