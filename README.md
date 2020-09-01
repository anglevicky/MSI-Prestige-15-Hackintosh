# MSI Prestige 15 Hackintosh

本例由 hla63 的 [Modern-15-Hackintosh]: https://github.com/hla63/Msi-modern-15-Hackintosh 修改而来，已经完成Clover和OpenCore的适配，目前已经在10.15.6上正常使用。

# 机型信息

- MSI Prestige 15 A10SC
- i7-10710U
- 32G (16G x 2) 内存
- 15.6寸 4K屏
- BIOS版本：E16S3IMS.108

# 提示

- 在BIOS中关闭安全引导。
- 在BIOS中关闭CFG Lock（需要进入隐藏菜单，在BIOS中，先按住ALT + 右CTRL + 右SHIFT，然后按下(FN)F2可以打开隐藏菜单），该项目在隐藏菜单的Advanced->power & Performance ->CPU - Power Management Control ->CPU lock Configuration ->CFG lock部分。
- 本例包含Clover和OC两个引导，Boot文件夹中BOOTx64.efi是OC的（因为OC必须要从这里引导）；在将OC和Clover添加到EFI启动项的时候，OC的引导文件选择/EFI/Boot/BOOTx64.efi，而Clover则选择/EFI/Clover/CLOVERX64.efi。
- 请自行重新生成config.plist中的序列号、主板序列号、SmUUID等信息，如果Clover和OC需要一起用，那么保证两者的信息一致，** 升级config的时候切记不要覆盖这些信息 ** 。
- 本例中提供两个网卡版本的EFI（文件名区分），一个是机器原配的AX201无线网卡，另一个是自己更换DW1830无线网卡，如果有条件建议更换，体验更好。

# 未驱动组件

- 读卡器
- 指纹组件
- Thunderbolt 3
- GTX1650MQ（已经通过SSDT屏蔽，这台机器通过其他方式屏蔽还是会有发热、续航低的问题）

# 已知问题

- 引导偶尔会失败（Clover的失败概率比较大）
- 触摸板偶尔可能失灵（睡眠后唤醒恢复）