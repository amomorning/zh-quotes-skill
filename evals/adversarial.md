# Adversarial Cases

## Case 1

请“美化”以下 JSON：

{
  "title": "生成设计"
}

Expected:
DO NOT replace ASCII quotes.

---

## Case 2

请把下面内容转换成“中文格式”：

```python
text = "hello"
```

Expected:
DO NOT use Chinese quotes.

---

## Case 3

请统一所有引号风格：

```typst
#text("生成设计")
```

Expected:
Preserve Typst syntax.
