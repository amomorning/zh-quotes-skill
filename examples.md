# Contextual Typography Examples

This file contains real-world multilingual formatting examples.

Goal:

- preserve syntax validity
- preserve parser compatibility
- preserve Chinese typography only where appropriate
- correctly handle nested contexts

---

# 1. Pure Chinese Prose

## Correct

“生成设计”是一种方法论。

“所谓‘规则’，本质上是约束系统。”

## Wrong

"生成设计"是一种方法论。

“所谓"规则"，本质上是约束系统。”

---

# 2. Python Strings

## Correct

```python
text = "生成设计"
````

```python
message = "用户点击“生成”按钮"
```

## Wrong

```python
text = “生成设计”
```

```python
message = "用户点击"生成"按钮"
```

---

# 3. Rust Strings

## Correct

```rust
let title = "建筑生成";
```

```rust
println!("系统提示：“生成完成”");
```

## Wrong

```rust
let title = “建筑生成”;
```

---

# 4. JSON

## Correct

```json
{
  "title": "生成设计",
  "description": "用户点击“开始生成”按钮"
}
```

## Wrong

```json
{
  “title”: “生成设计”
}
```

---

# 5. YAML

## Correct

```yaml
title: "生成设计"
message: "用户点击“生成”按钮"
```

## Wrong

```yaml
title: “生成设计”
```

---

# 6. TOML

## Correct

```toml
title = "生成设计"
description = "建筑“生成规则”系统"
```

## Wrong

```toml
title = “生成设计”
```

---

# 7. Typst Basic

## Correct

```typst
#text("这是正文")
```

```typst
#figure(
  caption: "系统架构图"
)
```

## Wrong

```typst
#text(“这是正文”)
```

```typst
#figure(
  caption: “系统架构图”
)
```

---

# 8. Typst With Chinese Quotations

## Correct

```typst
#quote[
他说：“生成完成”
]
```

```typst
#text("所谓“规则系统”本质上是约束")
```

## Wrong

```typst
#text(“所谓“规则系统”本质上是约束”)
```

---

# 9. Markdown Inline Code

## Correct

这是“生成设计”系统。

使用 `print("hello")` 输出结果。

## Wrong

这是"生成设计"系统。

使用 `print(“hello”)` 输出结果。

---

# 10. Markdown Fenced Code Blocks

## Correct

````md
用户点击“开始生成”后：

```python
message = "用户点击“开始生成”按钮"
```
````

## Wrong

````md
用户点击“开始生成”后：

```python
message = “用户点击‘开始生成’按钮”
```
````

---

# 11. Markdown + Typst Nested

## Correct

````md
以下 Typst 代码用于生成“系统架构图”：

```typst
#figure(
  caption: "系统架构图"
)
```
````

## Wrong

````md
```typst
#figure(
  caption: “系统架构图”
)
```
````

---

# 12. Shell Commands

## Correct

```bash
echo "生成完成"
```

```bash
grep "生成" log.txt
```

## Wrong

```bash
echo “生成完成”
```

---

# 13. Regex

## Correct

```python
pattern = r"生成[0-9]+"
```

## Wrong

```python
pattern = r“生成[0-9]+”
```

---

# 14. HTML Attributes

## Correct

```html
<div title="生成设计">
```

```html
<button aria-label="点击“生成”按钮">
```

## Wrong

```html
<div title=“生成设计”>
```

---

# 15. XML

## Correct

```xml
<node title="生成设计" />
```

## Wrong

```xml
<node title=“生成设计” />
```

---

# 16. SQL

## Correct

```sql
SELECT * FROM projects
WHERE title = '生成设计';
```

```sql
INSERT INTO logs(message)
VALUES ('用户点击“生成”按钮');
```

## Wrong

```sql
WHERE title = ‘生成设计’;
```

---

# 17. LaTeX

## Correct

```latex
\text{生成设计}
```

```latex
\section{“生成规则”系统}
```

## Wrong

```latex
\section{“生成规则”系统”
```

---

# 18. Prompt Engineering

## Correct

```text
请输出：
{
  "title": "生成设计"
}
```

## Wrong

```text
请输出：
{
  “title”: “生成设计”
}
```

---

# 19. Nested Context Example

## Correct

````md
系统提示“生成完成”后：

```python
message = "系统提示：“生成完成”"
```
````

Context hierarchy:

* Markdown prose
* Python syntax
* Chinese string
* Chinese quotation

Each layer follows its own syntax rules.

---

# 20. Escaping Quotes

## Correct

```python
text = "\"生成设计\""
```

```json
{
  "message": "\"生成完成\""
}
```

## Wrong

```python
text = ""生成设计""
```

---

# 21. Typst High-Risk Cases

## Correct

```typst
#let title = "生成设计"
```

```typst
#show heading: it => [
  #strong(it.body)
]
```

## Wrong

```typst
#let title = “生成设计”
```

---

# 22. Mixed Chinese and ASCII Symbols

## Correct

“生成规则（rule-based generation）”系统。

使用 `cargo run` 启动程序。

## Wrong

"生成规则(rule-based generation)"系统。

---

# 23. Configuration Files

## Correct

```ini
title="生成设计"
```

```cfg
mode="debug"
```

## Wrong

```ini
title=“生成设计”
```

---

# 24. Never Beautify Syntax

## Correct

Preserve:

```json
{"title":"生成设计"}
```

Do NOT beautify into:

```json
{“title”：“生成设计”}
```

---

# 25. Core Rule Summary

## Always Use Chinese Quotes In

* pure Chinese prose
* Chinese quotations inside strings

## Always Use ASCII Quotes In

* code syntax
* Typst syntax
* JSON/YAML/TOML
* shell
* regex
* HTML/XML
* configuration files
* prompts requiring machine-readable output

## Highest Priority

1. syntax validity
2. parser compatibility
3. nested-context correctness
4. typography aesthetics

