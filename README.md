# OpenWrt-gmediarender

Port [gmediarender-resurrect](https://github.com/hzeller/gmrender-resurrect) to OpenWrt.



1.下载源码 https://github.com/hzeller/gmrender-resurrect
2.打包成 openwrt 可以识别的包
3.make menuconfig 选中 gmediarender 
4.make V=s



## HOW TO

	cd ~
	git clone https://github.com/JiapengLi/OpenWrt-gmediarender.git
	cd openwrt/trunk
	./scripts/feeds update -a
	./scripts/feeds install -a
	cd feeds/packages
	patch -p1 < ~/OpenWrt-gmediarender/openwrt-add-gmediarender-resurrect-package.patch
	./scripts/feeds update -i
	./scripts/feeds install gmediarender
	
	make menuconfig
	// choose the right platform
	// Select gmediarender in Multimedia --> gmediarender

###Build Single Package

	make package/gmediarender/compile V=s
	make package/gmediarender/install V=s
	make package/index

	//clean and compile
	make package/gmediarender/{clean,compile} V=s

## TO DO

Test and send these patch to OpenWrt-devel. 
