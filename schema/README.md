# 图式

即细粒度高的心智模型。

## 格式

```yaml
- id: <uuid>
  label: "<名称>"
  entities:
    - name: <实体1>
      attributes:
        - <属性1>
        - <属性2>
    - name: <实体2>
      attributes:
        - <属性1>
        - <属性2>
  causals:
    - condition: "<条件>"
      outcome: "<结果>"
    - condition: "<条件>"
      outcome: "<结果>"
  boundaries:
    - "<边界条件>"
    - "<边界条件>"
  properties:
    - key: <属性1>
      value: "<值>"
    - key: <属性2>
      value: "<值>"
  dynamics:
    - key: <时间属性>
      value: "<值>"
  mappings:
    - intent: "<意图>"
      action: "<操作>"
    - intent: "<意图>"
      action: ["<操作1>", "<操作2>"]
  biases:
    - id: <uuid>
      belief: "<误解信念>"
      fact: "<事实>"
```

## 示例

```yaml
- id: <uuid>
  label: "智能恒温器"
  entities:
    - name: 恒温器
      attributes:
        - current_temperature
        - target_temperature
        - mode
    - name: 温度传感器
      attributes:
        - measures_indoor_temperature
    - name: 加热制冷设备
      attributes:
        - status
        - power
  causals:
    - condition: "target_temperature > current_temperature"
      outcome: "设备开始制热"
    - condition: "target_temperature <= current_temperature"
      outcome: "设备停止工作"
  boundaries:
    - "仅适用于住宅单一房间"
    - "忽略室外温度影响"
    - "不考虑设备延迟"
  properties:
    - key: 设备类型
      value: "分体式空调"
    - key: 工作模式
      value: "制冷"
  dynamics:
    - key: heating_rate
      value: "0.5 摄氏度/分钟"
    - key: natural_cooling_rate
      value: "0.2 摄氏度/分钟"
    - key: startup_delay
      value: "0 秒"
  mappings:
    - intent: "变暖和"
      action: "调高设定温度"
    - intent: "省电"
      action: ["切换到节能模式", "降低设定温度"]
  biases:
    - id: <uuid>
      belief: "认为设定温度越高，制热越快"
      fact: "实际功率恒定，仅终点温度更高"
    - id: <uuid>
      belief: "认为频繁开关设备更省电"
      fact: "频繁启动反而增加能耗"
```
