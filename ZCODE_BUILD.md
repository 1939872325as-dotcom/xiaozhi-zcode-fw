# zcode 临时构建分支

为 正点原子 ATK-DNESP32S3 编一个打了补丁的固件。

补丁内容 (main/audio/codecs/es8388_audio_codec.cc):
- codec 的 I2C 事务失败时重试(原代码一次失败即 abort 重启)
- esp_codec_dev_* 调用失败只告警, 不再终止设备
- 打开输入后回读 ES8388 寄存器并打印到日志
- MIC PGA 写入手册有效上限 0x88 (+24dB)

CI 变体清单已临时裁剪为只含 atk-dnesp32s3, 编译完成后本 fork 会被删除。
