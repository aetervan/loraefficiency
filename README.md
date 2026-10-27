# loraefficiency

**算清微调任务的资源消耗。**

`loraefficiency` —— 汇总显存、训练时长与推理成本，给出效率指标

- 零依赖，Python 3.10+ 标准库即可运行
- 单文件，`loraefficiency.py` 拷走就能用
- 不联网、不写文件

<!-- ipos:install -->
## 安装

零依赖，Python 3.10+ 即可：

```bash
pip install aetervan-loraefficiency
```

装完直接用命令名调用：

```bash
loraefficiency --help
```

也可以不用安装，直接把 `loraefficiency.py` 拷走用——它只依赖标准库。

## 为什么需要它

效率指标要和效果一起看，否则无法判断值不值

它遵守下面几条自己定的规矩：

1. **只报告能定位到具体位置的结论**，不做语义猜测。
2. **规则表公开**，每条命中都能对应到 微调资源效率 领域的一条明示规则。
3. **输入为空或格式不对时明确报错**，不静默返回空结果。

## 用法

```bash
python loraefficiency.py --file input.txt
python loraefficiency.py --text "示例内容"
python loraefficiency.py --file input.txt --json
```

加 `--json` 可以拿到机器可读的结果，便于接到流水线里。

## 已知局限

- 比例的分母取自你给的口径，不替你选口径。
- 不判断比例高低是否合理。

## 跑测试

```bash
python test_loraefficiency.py
```

测试用独立的断言与临时数据，不污染工作目录。

## 来源与参考

- Python 标准库文档：<https://docs.python.org/3/>
- GitHub 仓库：<https://github.com/aetervan/loraefficiency>

---

## 关于作者

aetervan 做微调资源效率相关的问题。这个工具先替你回答一个具体问题，再谈别的。

- 个人主页：<https://aetervan.github.io>
- 仓库：<https://github.com/aetervan/loraefficiency>

## 许可

MIT，见 [LICENSE](LICENSE)。
