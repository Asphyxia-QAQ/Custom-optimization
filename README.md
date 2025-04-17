## **定制优化v4.3.2-250417**

  - **更新日志**
    
    - 新增 优化[perfboost] 选项，选用后会调整系统boost，使其不那么激进(夏天到了.jpg)，建议配合 [定制温控] 使用，也可配合 [第三方调度]
    
    - 调整 [doze白名单] 默认清理，不设置选项
    
    - 调整 [内存管理优化] 参数
    
    - 调整 [system.prop]
    
    - 调整 [CPUset]
    
    - 修复 [脚本错误]
    
    - 同步 [VoyagerKernel Modules] 更新，确保内核版本为 b400-250411 否则后果自负
    
  - **模块介绍**
  
    - ①优化云控，基于 'K60' 最新云控制作
    
    - ②Boost，cpuset等优化调整
    
    - ③内存管理优化-MemOpt，优化后台留存，调整zram，vm，lmkd等参数 [Some of the content comes from 'scene附加模块二' ]
    
    - ④prop优化调整 [Prop From Kernel-Pandora-5.10 Derive]，优化核心分配，dex2oat，ART等内容
    
    - ⑤[去除doze白名单] 让应用息屏进入doze，避免应用息屏耗电，[微信] [小米服务框架] [scene] 默认加入白名单，避免息屏doze掉后台/推送延迟
    
    - [doze白名单] 会被系统恢复，必须使用相关模块hook屏蔽，如：西米露→电量与性能→禁止恢复电池优化白名单，打开之后才不会被系统恢复
    
    - ⑥来自Pandora的 [dex2oat] 优化，虽然会导致安装应用速度下降，但利大于弊，建议勾选
    
    - ⑦内置 [VoyagerKernel] 内核模块，可直接代替vk附加模块使用
    
    - ⑧模块适配 [REDMI K50 Ultra] [REDMI K60] [Xiaomi 12S Pro] [Xiaomi 12S Ultra]。若刷入 [VoyagerKernel] Vk内核则支持taro所有机型 "SM8450 8475 7475"
    
    (使用本模块可能出现 [不开机] 等各种故障，如若出现可选择卸载本模块)
    
    (若无看完模块说明，不了解强行刷入该模块，导致卡米等问题自行解决)

  -  **注意事项**
    
      - 与 [Kernel-Pandora-5.10] 严重冲突，人家比我做得更好更合适，模块已做禁止刷入处理，若共存，一切后果自负
   
      - 与 [内存管理优化] 相关 'magisk'模块 冲突，与lsp模块一般不冲突，可配合使用
   
      - 与 [相同优化云控类模块] 冲突
   
      - 与 [相同优化prop类模块] 冲突
   
      - 与 [uperf (yc调度) ] 冲突
   
      - 建议与 [scene LP | HP] 使用
   
      - 建议与 [AsoulOpt] 'mode=2' 使用，记得关闭scene核心分配中对游戏的作用域
   
      - 不与 [fas rs] 本体冲突，相关插件具体辨别
   
      - 请关闭 [scene→SWAP设置→自启动] 再使用 模块内 [内存管理优化-MemOpt] 否则有异常自行解决，也无需反馈
   
      - 建议在 [官方最新系统] 下使用，请勿在 <非MIUI/Hyper> 的移植包下使用
   
      - 若官改/移植使用模块中出现异常，请自行解决或恢复官方环境，我无法兼容所有环境
   
      - 非 [官方最新系统] 下使用出现异常，请自行解决或更新至最新系统，考古导致的一切异常概不负责
    
      - 卸载模块之后会导致模糊丢失，不用担心，再重启一次就行，因为模块加入了打开模糊相关的prop，模块卸载会自动清除，避免残留


## **模块内容**

  - **云控**
  
    - ①去除云控内所有锁帧，降分辨率，锁频等内容
    
    - ②为云控添加额外内容：原神分辨率切换等
    
    - ③[12sp]与[12su]的migt云控仅做去除锁帧，降分辨率，添加额外内容，其他与官方保持一致
    
    - ④优化云控，适配更多游戏：若游戏未适配/效果不佳 可反馈/适配调整，或使用 [scene LP | HP]，调度会自行打开 [Xiaomi FEAS]
    
    - ⑤适配游戏较多，不再赘述，若在 [官方调度] 下没有启用 [FEAS] 则证明云控内并未适配此游戏，可向我提供 [游戏包名] 与 [游戏最高帧率]，有空我会适配
    
  
  - **VoyagerKernel Modules**
  
    - ①确保内核版本为 b400-250411 否则后果自负
    
    - ②此版本无时间测试适合作业，可照搬上个版本的作业，效果一样优秀，调速器可在 [ROOT管理器：magisk/ksu等] 自行切换 <操作/执行>
    
    - ③作业：[vk+fas rs(4.8.0)+asoul mode=0]，此搭配效果良好，经回放测试帧率与功耗表现优秀
    
    (若刷入 [VoyagerKernel] 前已使用 [定制优化] 则必须重新刷入一次，更换内核前请 <卸载模块重启后> 更换)
    
  - **内存管理优化-MemOpt**
  
    - ①默认zram大小为1:1.5
    - ②模块会自行关闭ExtM，别问我为什么没开ExtM，没任何理由使用，想使用就不要在模块内选择该选项
