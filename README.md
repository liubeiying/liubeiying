# 刘蓓颖

南京航空航天大学 · 机器人工程 · 2027 届本科
方向：人形机器人运动控制 · 灵巧手上肢操作 · sim-to-real

---

## 关于这个账号

这个账号下的仓库是**复现与工程记录**，不是原创算法仓库。

训练框架、机器人模型、控制算法都来自上游开源项目，版权归原作者所有。我做的事情是：在自己的环境里把它们跑通、调通，并把每一步的参数、现象和踩过的坑记下来。每个仓库首页都写了上游来源，可以直接对照。

我把这些过程整理成文档，是因为复现本身就有工作量——同样的代码在不同环境下能跑出完全不同的结果，中间那些"为什么跑不通"的排查过程，是我真正学到的东西。

---

## 仓库

| 仓库 | 内容 |
|---|---|
| [g1-locomotion-rl](https://github.com/liubeiying/g1-locomotion-rl) | Unitree G1 行走策略：Isaac Gym 训练 → MuJoCo 验证 → ROS 2 下发 |
| [leap-hand-manipulation](https://github.com/liubeiying/leap-hand-manipulation) | LEAP Hand 灵巧手：仿真搭建、自由度对齐、抓取动作开发、硬件联调 |
| [sim2real-playbook](https://github.com/liubeiying/sim2real-playbook) | sim-to-real 排查手册：观测对齐 / URDF·MJCF 对表 / PD 与执行器 / 频率与延迟 |

---

## 我走过的链路

```
仿真搭建 → 模型校验 → 策略训练 → sim2sim 验证 → 真机部署 → 问题回灌训练
                                                              ↑            │
                                                              └────────────┘
```

- **仿真**：Isaac Gym / legged_gym / rsl_rl / MuJoCo / mujoco_menagerie
- **部署**：ROS 2 Humble + CycloneDDS，TorchScript / ONNX 策略加载
- **硬件**：CAN FD / RS485 / Modbus，指尖触觉读取，终端电阻与驱动排查
- **工程**：训练—导出—部署脚本化，环境与排错文档化

---

## 我记文档的习惯

- 每个结论标注实验前提与风险点，让别人能照着复现
- 已知边界如实写，比如真机受指尖传感器噪声影响存在波动
- 安全规则写进代码而不是写在脑子里：二次确认、超限直接拒绝输出、调试分级

---

## 上游致谢

legged_gym · rsl_rl · unitree_rl_gym · unitree_ros · unitree_mujoco ·
mujoco · mujoco_menagerie · mujoco_playground ·
LEAP_Hand_Sim · LEAP_Hand_API · humanoid-gym · IsaacLab

---

2080571809@qq.com
