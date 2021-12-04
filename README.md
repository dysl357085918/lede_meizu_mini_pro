# lede_meizu_mini_pro
对魅族路由器mini双频版本的openwrt/lede适配，因为不完美（荒野无灯啊），所以不提交到lede上了，本来用的人就少。感谢原项目，这里只是说明如何修改。

lede源码修改/添加以下文件（可以自己比对修改了哪里，也可以直接拿去）

1.替换lede/target/linux/ramips/mt76x8/base-files/etc/board.d/01_leds 
2.替换lede/target/linux/ramips/mt76x8/base-files/etc/board.d/02_network
3. lede/target/linux/ramips/dts/ 内添加mt7628an_meizu_mini.dts和mt7628an_meizu_hc5x61a.dtsi
4. lede/target/linux/ramips/image/mt76x8.mk替换

我一共改了这五个地方

刷openwrt前，建议先刷入breed
然后从breed刷入openwrt
这里附件一个我编译好的，没啥特殊功能的固件。
这孱弱的性能拿来科学上网太吃力了。
