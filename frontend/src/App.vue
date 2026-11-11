<template>
  <div class="app-shell">
    <aside class="app-side">
      <h1 class="app-title">数据洞察分析工作台</h1>
      <nav class="nav-list">
        <RouterLink v-for="item in navItems" :key="item.path" :to="item.path" class="nav-item">
          {{ item.label }}
        </RouterLink>
      </nav>
    </aside>
    <main class="app-main">
      <header class="app-head">
        <span class="head-desc">面向多源数据接入、交互式查询分析、可视化看板搭建、分析报告生成与数据服务编排的数据洞察分析工作台。</span>
        <span class="head-user">当前值班：{{ store.operator }} · {{ store.shiftLabel }}</span>
      </header>
      <RouterView />
    </main>
  </div>
</template>

<script setup lang="ts">
import { useSessionStore } from '@/stores/session'

const store = useSessionStore()

const navItems = [{ label: "运营概览", path: "/" }, { label: "交互查询", path: "/query" }, { label: "可视化图表", path: "/chart" }, { label: "数据源接入", path: "/source" }, { label: "聚合计算", path: "/aggregate" }, { label: "数据筛选", path: "/filter" }, { label: "报告生成", path: "/reportgen" }, { label: "异常检测", path: "/anomaly" }, { label: "多维下钻", path: "/drill" }, { label: "对比分析", path: "/compare" }, { label: "分析流水线", path: "/pipeline" }, { label: "数据集管理", path: "/datastore" }, { label: "趋势预测", path: "/forecast" }, { label: "数据分片", path: "/segment" }, { label: "调度管理", path: "/scheduler" }, { label: "通知分发", path: "/notify" }, { label: "查询缓存", path: "/cache" }, { label: "数据标签", path: "/tag" }, { label: "数据分享", path: "/share" }]
</script>
