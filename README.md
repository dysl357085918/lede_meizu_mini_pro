# lede_meizu_mini_pro
对魅族路由器mini双频版本的openwrt/lede适配，因为不完美（荒野无灯啊），网口和双频wif正常，恢复建正常。。所以不提交到lede上了，本来用的人就少。感谢原项目，这里只是说明如何修改。

lede源码修改/添加以下文件（可以自己比对修改了哪里，也可以直接拿去）

1.替换lede/target/linux/ramips/mt76x8/base-files/etc/board.d/01_leds 
2.替换lede/target/linux/ramips/mt76x8/base-files/etc/board.d/02_network
3. lede/target/linux/ramips/dts/ 内添加mt7628an_meizu_mini.dts和mt7628an_meizu_hc5x61a.dtsi
4. lede/target/linux/ramips/image/mt76x8.mk替换

我一共改了这五个地方
然后编译



如何刷入：

1.padavan下先刷入breed，breed版本是breed-mt76x8-blank.bin,可从恩山等地找到教程，
这里注意，因为用的是通用的breed，本身并没有设置reset键。需要用breedenter才能进入breed，
之后可以修改环境变量指定一个自定义复位键配置，这里是38L. env set gpio.customized.reset 38L

#breed刷入教程参考https://www.right.com.cn/forum/thread-161906-1-1.html
有breed就是随便刷，刷不死了。

2.然后从breed刷入编译好的openwrt

这里附件一个我编译好的，有bypass的固件，内含ss+obfs，不含别的，这性能弄别的也很慢.
