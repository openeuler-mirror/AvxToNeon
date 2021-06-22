# AvxToNeon

#### 介绍
x86平台到鲲鹏平台迁移的系统加速库。
当使用Intel intrinsic的应用程序从x86平台迁移到鲲鹏平台时，由于两平台之间指令的区别，需要基于Arm64指令对相对应的intrinsic作迁移与优化。为了减少用户在迁移过程中的工作量，我们基于NEON SIMD提供了适配于鲲鹏平台的指令，这些指令与x86 intrinsic同名、同功能。用户只需替换头文件即可完成迁移。

#### 软件架构
- data 测试数据文件夹
- tests 测试代码
- avx2neon.h 对外头文件
- avx512intrin.h 内部头文件
- avxintrin.h 内部头文件
- emmintrin.h 内部头文件
- immintrin.h 内部头文件
- typedefs.h 内部头文件
- supportedlist.md 支持接口列表

#### 使用说明

1.  获得AvxToNeon源码
2.  屏蔽软件中的immintrin.h
3.  在应用中包含avx2neon.h
4.  添加编译选项，ARCH_CFLAGS = -march=armv8-a+fp+simd+crc

#### License

[APACHE LICENSE, VERSION 2.0](https://www.apache.org/licenses/LICENSE-2.0)

#### 测试

tests是测试代码目录，data是测试数据目录，测试步骤如下：

```
(1) cd tests
(2) make
(3) ./test
```

执行命令后会输出以下信息：

```
Running Test MM512_CASTPS128_PS512

...

Running Test MM256_SET_EPI32

AVX2NEONTest Complete: Passed 265 tests: Failed 0
```

所有接口均在以下场景通过验证：操作系统 OpenEuler 20.03 LTS SP1 和 CentOS Linux release 7.6.1810 (AltArch) ，编译器版本 GCC 7.3, GCC 4.8.5, GCC 9.2.0

#### 更多信息

更多信息请浏览

<https://www.huaweicloud.com/kunpeng/software.html>

如果您有任何问题或建议，可以在gitee上提出issue。或者直接发送邮件联系我们的开发团队

 [kunpengcompute@huawei.com](mailto:kunpengcompute@huawei.com).

#### 获得代码

如果您想获得supportedlist.md上的全部接口，请发送邮件至 [kunpengcompute@huawei.com]

#### 参与贡献

1.  Fork 本仓库
2.  新建 Feat_xxx 分支
3.  提交代码
4.  新建 Pull Request

#### 版权声明

Copyright © 2020 Huawei Corporation. All rights reserved. 
