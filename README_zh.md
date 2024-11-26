# excelize-py

<p align="center"><img width="500" src="https://github.com/xuri/excelize-py/raw/main/excelize-py.svg" alt="excelize-py logo"></p>

<p align="center">
    <a href="https://pypi.org/project/excelize"><img src="https://img.shields.io/pypi/v/excelize.svg" alt="Pipy version"></a>
    <a href="https://github.com/xuri/excelize-py/actions/workflows/build.yml"><img src="https://github.com/xuri/excelize-py/actions/workflows/build.yml/badge.svg" alt="Build Status"></a>
    <a href="https://codecov.io/gh/xuri/excelize-py"><img src="https://codecov.io/gh/xuri/excelize-py/branch/main/graph/badge.svg" alt="Code Coverage"></a>
    <a href="https://opensource.org/licenses/BSD-3-Clause"><img src="https://img.shields.io/badge/license-bsd-orange.svg" alt="Licenses"></a>
    <a href="https://www.paypal.com/paypalme/xuri"><img src="https://img.shields.io/badge/Donate-PayPal-green.svg" alt="Donate"></a>
</p>

excelize-py 是 Go 语言 [Excelize](https://github.com/xuri/excelize) 基础库的 Python 实现，可用于操作 Office Excel 文档，基于 ECMA-376，ISO/IEC 29500 国际标准。可以使用它来读取、写入由 Microsoft Excel&trade; 2007 及以上版本创建的电子表格文档。支持 XLAM / XLSM / XLSX / XLTM / XLTX 等多种文档格式，高度兼容带有样式、图片(表)、透视表、切片器等复杂组件的文档。可应用于各类报表平台、云计算、边缘计算等系统。获取更多信息请访问 [参考文档](https://xuri.me/excelize/)。

## 运行环境兼容性

操作系统 | CPU 架构
---|---
Windows | amd64
Darwin | amd64
Darwin | arm64
Linux | amd64
Linux | arm64

## 快速上手

### 安装

```bash
pip install excelize
```

### 创建 Excel 文档

下面是一个创建 Excel 文档的简单例子：

```python
import excelize

f = excelize.new_file()
# 新建一张工作表
index, err = f.new_sheet("Sheet2")
if err is not None:
    print(err)
    exit()
# 设置单元格的值
f.set_cell_value("Sheet2", "A2", "Hello world.")
f.set_cell_value("Sheet1", "B2", 100)
# 设置工作簿的默认工作表
f.set_active_sheet(index)
# 根据指定路径保存文件
err = f.save_as("Book1.xlsx")
if err is not None: {
    print(err)
}
err = f.close()
if err is not None: {
    print(err)
}
```

## 社区合作

欢迎您为此项目贡献代码，提出建议或问题、修复 Bug 以及参与讨论对新功能的想法。

## 开源许可

本项目遵循 BSD 3-Clause 开源许可协议，访问 [https://opensource.org/licenses/BSD-3-Clause](https://opensource.org/licenses/BSD-3-Clause) 查看许可协议文件。

Excel 徽标是 [Microsoft Corporation](https://aka.ms/trademarks-usage) 的商标，项目的图片是一种改编。

gopher.{ai,svg,png} 由 [Takuya Ueda](https://twitter.com/tenntenn) 创作，遵循 [Creative Commons 3.0 Attributions license](http://creativecommons.org/licenses/by/3.0/) 创作共用授权条款。