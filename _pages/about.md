---
layout: about
title: 首页 @ about
permalink: /
subtitle: <span class="lang-zh"><a href='https://www.zju.edu.cn/'>浙江大学</a> · <a href='https://www.berkeley.edu/'>加州大学伯克利分校</a> | 城市交通 · 地理空间人工智能 · 城市分析</span><span class="lang-en"><a href='https://www.zju.edu.cn/'>Zhejiang University</a> · <a href='https://www.berkeley.edu/'>UC Berkeley</a> | Urban Transportation · GeoAI · Urban Analytics</span>

# 布局说明：照片与联系信息固定在左栏，简介与研究内容固定在右栏（互不环绕），
# 两栏宽度在 _layouts/about.liquid 中定义（col-sm-4 / col-sm-8）。
# 正文用 lang-zh / lang-en 两块实现中英双语，右上角按钮切换。
profile:
  image: prof_pic.jpg
  image_circular: false
  more_info: >
    <p><span class="lang-zh">浙江大学 博士生</span><span class="lang-en">Ph.D. Student, Zhejiang University</span></p>
    <p><span class="lang-zh">加州大学伯克利分校 访问学者</span><span class="lang-en">Visiting Scholar, UC Berkeley</span></p>

selected_papers: true # includes a list of papers marked as "selected={true}"
social: true # includes social icons at the bottom of the page

announcements:
  enabled: true # includes a list of news items
  scrollable: true # adds a vertical scroll bar if there are more than 3 news items
  limit: 5 # leave blank to include all the news in the `_news` folder

latest_posts:
  enabled: false # 暂时隐藏"最新文章"区块，需要时改回 true
  scrollable: true
  limit: 3 # leave blank to include all the blog posts
---

<div class="lang-zh" markdown="1">

你好，我是**郭文彤** 👋，浙江大学交通运输工程专业博士生，我的博士导师是金盛教授。目前，我在加州大学伯克利分校景观建筑与环境规划系开展访问研究，并在 3M Lab 与 Lu Liang 教授合作开展研究。

我的研究位于城市交通、地理空间人工智能（GeoAI）与城市计算（Urban Computing）的交叉领域，关注如何利用多源城市数据和人工智能理解复杂城市系统中的人类活动、交通运行与环境过程，并进一步支持更加安全、高效、韧性和以人为本的城市决策：

- 🚗 **城市移动性与交通安全**：基于轨迹、路网与交通状态数据，研究城市交通风险感知、安全路径规划与协同优化。

- 🧠 **地理空间人工智能与多模态城市智能**：融合遥感、街景、轨迹与城市空间数据，开展多模态城市感知、预测与解释。

- 🤖 **城市智能体与世界模型**：面向复杂城市交通系统，探索智能体行为建模、状态演化模拟与自主决策优化。

- 🌡️ **城市气候、人类移动与暴露**：研究城市热环境与人类活动的时空耦合，以及动态暴露、不平等与城市韧性。

- ⚡ **城市能源与智能基础设施**：面向电动汽车与城市能源系统，研究需求预测、空间建模与基础设施智能优化。

</div>

<div class="lang-en" markdown="1">

Hi, I am **Wentong Guo** 👋, a Ph.D. student in Transportation Engineering at Zhejiang University, supervised by Prof. Sheng Jin. I am currently a visiting scholar in the Department of Landscape Architecture and Environmental Planning at UC Berkeley, collaborating with Prof. Lu Liang at the 3M Lab.

My research lies at the intersection of urban transportation, geospatial artificial intelligence (GeoAI), and urban computing. I focus on leveraging multi-source urban data and AI to understand human activities, traffic operations, and environmental processes in complex urban systems, and to support safer, more efficient, more resilient, and human-centered urban decision-making:

- 🚗 **Urban Mobility & Transportation Safety**: traffic risk perception, safety-aware route planning, and cooperative optimization based on trajectory, road network, and traffic state data.

- 🧠 **GeoAI & Multimodal Urban Intelligence**: multimodal urban sensing, prediction, and interpretation by fusing remote sensing, street view, trajectory, and urban spatial data.

- 🤖 **Urban Agents & World Models**: agent behavior modeling, system evolution simulation, and autonomous decision optimization for complex urban transportation systems.

- 🌡️ **Urban Climate, Human Mobility & Exposure**: spatiotemporal coupling between urban heat and human activities, dynamic exposure, spatial inequality, and urban resilience.

- ⚡ **Urban Energy & Intelligent Infrastructure**: demand forecasting, spatial modeling, and intelligent optimization of infrastructure for EVs and urban energy systems.

</div>

<!-- 分栏点：下面这条注释以上内容显示在照片右侧，以下内容全宽显示在照片下方 -->
<!-- split -->

<div class="lang-zh" markdown="1">

我尤其关注这样一个核心问题：

> **如何利用多模态城市数据与空间人工智能，来理解、预测并优化复杂的城市系统？**

近期研究包括城市道路交通风险建模与安全路径优化、多源城市数据驱动的 EV 充电需求预测、城市活动空间与极端热暴露耦合分析，以及面向未来城市交通系统的 Agent / World Model 建模。

</div>

<div class="lang-en" markdown="1">

I am particularly interested in one core question:

> **How can multimodal urban data and spatial AI be used to understand, predict, and optimize complex urban systems?**

My recent work includes urban road traffic risk modeling and safety-aware route optimization, multi-source data-driven EV charging demand forecasting, coupling analysis of urban activity space and extreme heat exposure, and Agent / World Model modeling for future urban transportation systems.

</div>

## <span class="lang-zh">精选研究</span><span class="lang-en">Featured Research</span>

<!-- 卡片内容在 _data/featured_research.yml 中维护（加项目只需加几行），
     支持横向拖动 / 滚动条拉动 / 左右箭头浏览 -->
{% include carousel.liquid %}
