# 图式

即细粒度高的心智模型。

## 格式

```yaml
- id: <uuid>
  label: "<名称>"
  content:
    usage: "<适用场景说明>"
    entities:
      - name: <实体名>
        attributes:
          - <属性1>
          - <属性2>
    causals:
      - condition: "<条件>"
        outcome: "<结果>"
    boundaries:
      - "<边界条件1>"
      - "<边界条件2>"
    properties:
      - key: "<参数名>"
        value: "<值>"
    mappings:
      - intent: "<意图>"
        action: "<操作>"
    biases:
      - id: <uuid>
        belief: "<误解信念>"
        fact: "<事实>"
```

## 示例

```yaml
- id: a1b2c3d4-e5f6-7890-abcd-ef1234567890
  label: 商务拓展
  content:
    usage: 适用于产品经理和创业者评估新想法时参考
    entities:
      - name: 新想法
        attributes:
          - 可行性
          - 门槛
      - name: 验证手段
        attributes:
          - POC
          - 章程
          - 原型
    causals:
      - condition: 新想法通过低门槛验证
        outcome: 可行后结构化复制
      - condition: 验证失败
        outcome: 低成本放弃
    boundaries:
      - 适用于商业和研发探索
      - 排除高投入长期项目
    properties:
      - key: 验证成本
        value: 低
    mappings:
      - intent: 探索新商业模式
        action: 做POC验证
    biases:
      - id: b1c2d3e4-...
        belief: 所有想法都值得先投入
        fact: 低门槛验证可快速筛选无效想法
```
