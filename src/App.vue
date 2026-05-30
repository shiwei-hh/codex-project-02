<template>
  <header class="site-header" aria-label="主导航">
    <a class="brand" href="#top" aria-label="禾味小馆首页">
      <span class="brand-mark">禾</span>
      <span>禾味小馆</span>
    </a>
    <nav class="nav-links" aria-label="页面导航">
      <a v-for="link in navLinks" :key="link.href" :href="link.href">
        {{ link.label }}
      </a>
    </nav>
    <a class="header-action" href="tel:4001886626">预订</a>
  </header>

  <main id="top">
    <section class="hero" aria-labelledby="hero-title">
      <img
        class="hero-image"
        src="../assets/hero-table.png"
        alt="摆满招牌菜和米酿的餐桌插画"
      />
      <div class="hero-overlay"></div>
      <div class="hero-content">
        <p class="eyebrow">晚餐 · 小聚 · 城市烟火</p>
        <h1 id="hero-title">禾味小馆</h1>
        <p class="hero-copy">
          用当季食材做新派中式家常菜，明火快炒、手作点心和一杯刚好的桂花米酿。
        </p>
        <div class="hero-actions">
          <a class="primary-button" href="#menu">查看菜单</a>
          <a class="secondary-button" href="tel:4001886626">电话订座</a>
        </div>
      </div>
    </section>

    <section class="intro" aria-label="餐厅亮点">
      <div v-for="item in stats" :key="item.value">
        <span class="stat">{{ item.value }}</span>
        <p>{{ item.label }}</p>
      </div>
    </section>

    <section class="section" id="menu" aria-labelledby="menu-title">
      <div class="section-heading">
        <p class="eyebrow">Signature dishes</p>
        <h2 id="menu-title">今日招牌</h2>
      </div>
      <div class="dish-grid">
        <article v-for="dish in dishes" :key="dish.name" class="dish-card">
          <img :src="dish.image" :alt="dish.alt" />
          <div>
            <h3>{{ dish.name }}</h3>
            <p>{{ dish.description }}</p>
            <span>{{ dish.price }}</span>
          </div>
        </article>
      </div>
    </section>

    <section class="feature" id="space" aria-labelledby="space-title">
      <div class="feature-copy">
        <p class="eyebrow">Dining room</p>
        <h2 id="space-title">像回家一样，坐下来吃顿热饭</h2>
        <p>
          推门进来，有热汤的香气，也有轻声的问候。我们把灯光调得柔和，
          把菜做得暖胃，让家人、朋友和独自用餐的人，都能被一顿饭好好照顾。
        </p>
      </div>
      <img
        class="feature-image"
        src="../assets/dining-room.png"
        alt="温暖灯光下的餐厅用餐区插画"
      />
    </section>

    <section class="visit" id="visit" aria-labelledby="visit-title">
      <div>
        <p class="eyebrow">Visit us</p>
        <h2 id="visit-title">今晚来吃饭</h2>
        <p>上海市梧桐路 88 号 1F · 近地铁 2 号线</p>
      </div>
      <div class="visit-actions">
        <a class="primary-button" href="tel:4001886626">400-188-6626</a>
        <a class="secondary-button dark" href="mailto:hello@heweiguan.example">包间咨询</a>
      </div>
    </section>
  </main>
</template>

<script setup>
import dishChicken from "../assets/dish-chicken.png";
import dishSoup from "../assets/dish-soup.png";
import dishSeasonal from "../assets/dish-seasonal.png";

const navLinks = [
  { href: "#menu", label: "招牌菜" },
  { href: "#space", label: "用餐环境" },
  { href: "#visit", label: "到店" },
];

const stats = [
  { value: "16:30", label: "每日开始晚市" },
  { value: "38", label: "道当季小菜轮换" },
  { value: "3F", label: "临窗包间可预约" },
];

const dishes = [
  {
    name: "砂锅葱油鸡",
    description: "三黄鸡慢焖后淋热葱油，皮脆肉嫩，配自制豉油汁。",
    price: "¥48",
    image: dishChicken,
    alt: "砂锅葱油鸡菜品插画",
  },
  {
    name: "菌菇狮子头汤",
    description: "手打肉丸配松茸、竹荪与清鸡汤，汤色清亮，口感厚实。",
    price: "¥56",
    image: dishSoup,
    alt: "菌菇狮子头汤菜品插画",
  },
  {
    name: "时令小炒合盘",
    description: "芦笋、山药、鲜虾仁与木耳旺火快炒，清爽适合分享。",
    price: "¥58",
    image: dishSeasonal,
    alt: "时令小炒合盘菜品插画",
  },
];
</script>
