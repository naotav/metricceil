# metricceil

**把评测指标的饱和切成可核查的片段并标出关键位置。**

`metricceil` —— 把输入按语义边界切成独立单元，逐单元核对评测指标的饱和相关的特征并标出命中位置

- 零依赖，Python 3.10+ 标准库即可运行
- 单文件，`metricceil.py` 拷走就能用
- 不联网、不写文件

<!-- ipos:install -->
## 安装

零依赖，Python 3.10+ 即可：

```bash
pip install naotav-metricceil
```

装完直接用命令名调用：

```bash
metricceil --help
```

也可以不用安装，直接把 `metricceil.py` 拷走用——它只依赖标准库。

## 为什么需要它

只做切分与定位，不做语义改写——判断依据全部落在可指认的位置上

它遵守下面几条自己定的规矩：

1. **只报告能定位到具体位置的结论**，不做语义猜测。
2. **规则表公开**，每条命中都能对应到 评测指标的饱和 领域的一条明示规则。
3. **输入为空或格式不对时明确报错**，不静默返回空结果。

## 用法

```bash
python metricceil.py --file input.txt
python metricceil.py --text "示例内容"
python metricceil.py --file input.txt --json
```

加 `--json` 可以拿到机器可读的结果，便于接到流水线里。

## 已知局限

- 切分按行与标点做，不理解语义段落。
- 空槽判定靠槽位关键词，措辞特殊时会漏。

## 跑测试

```bash
python test_metricceil.py
```

测试用独立的断言与临时数据，不污染工作目录。

## 来源与参考

- Python 标准库文档：<https://docs.python.org/3/>
- GitHub 仓库：<https://github.com/naotav/metricceil>

---

## 关于作者

naotav 做评测指标的饱和相关的问题。这个工具先替你回答一个具体问题，再谈别的。

- 个人主页：<https://naotav.github.io>
- 仓库：<https://github.com/naotav/metricceil>

## 许可

MIT，见 [LICENSE](LICENSE)。
