# Nanshan Solar PV Prediction Results

南山区研究区建筑屋顶与立面光伏潜力预测结果。

## 数据内容

- 10,068 栋建筑的 EnergyPlus 24.2 模拟结果
- 建筑级 CSV、JSONL 与 GeoPackage
- 屋顶、立面及总发电量汇总
- 空间分布图与统计图
- 当前结果总量：屋顶 659.20 GWh、立面 511.78 GWh、合计 1,170.99 GWh

数据压缩包位于仓库的 **Releases** 页面；`MANIFEST.csv` 提供每个文件的相对路径、字节数和 SHA-256。

## 方法摘要

采用 Equivalent One-Diode 光伏模型和逐时动态外部建筑遮挡。屋顶可用比例为 64%，立面面积基于建筑墙体面积与 WWR 计算。

## 下载与校验

```bash
gh release download v1.0.0 --repo Aspartame-yao/nanshan-solar-pv-prediction-results
shasum -a 256 -c RELEASE_ASSETS.sha256
for file in *part-*.tar; do tar -xf "$file"; done
```

本仓库仅包含当前正式结果及图表，已排除失败运行目录、旧版本归档、天气文件、模型程序和所有密钥。
