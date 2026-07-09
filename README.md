# meta-custom-rules-dat

自定义 geosite 规则仓库，最小目标是自动产出两类规则文件：

- sing-box: `*.srs`
- mihomo / Clash Meta: `*.mrs`

当前规则：

- `custom-proxy`
- `custom-direct`

## 目录

```text
meta-custom-rules-dat/
  .github/workflows/build.yml
  data/
    custom-proxy
    custom-direct
```

## 输出分支

构建 workflow 会把产物推到三个分支：

- `release`: `geosite.dat`
- `sing`: `geosite/*.srs`
- `meta`: `geosite/*.mrs`

## 预期 URL

把仓库单独迁出去后，Worker 应引用：

- `https://raw.githubusercontent.com/leeechsh/meta-custom-rules-dat/sing/geosite/custom-proxy.srs`
- `https://raw.githubusercontent.com/leeechsh/meta-custom-rules-dat/sing/geosite/custom-direct.srs`
- `https://raw.githubusercontent.com/leeechsh/meta-custom-rules-dat/meta/geosite/custom-proxy.mrs`
- `https://raw.githubusercontent.com/leeechsh/meta-custom-rules-dat/meta/geosite/custom-direct.mrs`

## 规则格式

使用 `domain-list-community` / `domain-list-custom` 风格：

- 普通域名：`example.com`
- 精确域名：`full:example.com`
- 关键词：`keyword:example`
- 正则：`regexp:...`
